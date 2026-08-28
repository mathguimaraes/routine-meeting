---
layout: post
title: "4,015 Retries, Zero Audio: A Postmortem on the Microphone Pin Bug"
description: "How a feature meant to fix Bluetooth mic quality nearly lost an entire meeting's recording — and the fail-open fix that replaced it."
categories: [blog]
date: 2026-08-28
---

Someone asked for a small thing: "connecting my Bluetooth headphones makes macOS use their mic, and it sounds worse than my built-in one — can I pin recording to the built-in mic instead?" Reasonable ask. I shipped it in v1.2 as **Force Microphone Input**, under Settings → Advanced. Two versions later, that same feature caused a meeting to record 146 minutes of silence on one side and nobody noticed until it was too late to matter.

Here's what happened, and why the fix isn't "make the pin more reliable."

## The feature, and the warning I'd already written to myself

Pinning a specific input device on `AVAudioEngine` isn't officially supported the way you'd want it to be. The mechanism is `AudioUnitSetProperty(kAudioOutputUnitProperty_CurrentDevice)` on the engine's input node — a low-level Core Audio call that predates `AVAudioEngine` and doesn't coordinate cleanly with it. I'd flagged this exact combination as a risk in my own notes before ever writing the feature. I built it anyway, because the ask was reasonable and it worked fine in testing. The risk materialized later, exactly as predicted, just not in a way testing was ever going to catch.

## July 20th

The setup: pin set to the built-in mic, while a Bluetooth headset was the system's actual default input device. Every time the engine tried to reconcile "user wants built-in" against "system says Bluetooth," it triggered a config-change notification. Handling that notification meant re-pinning and restarting the engine. Restarting the engine triggered another config-change notification. That loop ran for the entire meeting: **4,015 recovery cycles in 146 minutes, and not one buffer of microphone audio was ever actually captured.**

The system-audio side — everyone else in the call — recorded fine. The transcript came out complete-looking, just one-sided, with nothing in the text itself to signal that half the conversation was structurally missing. That's the part that actually worried me: a silent, plausible-looking failure is worse than a loud one.

## Why I didn't just make the pin "smarter"

The tempting fix is to patch the retry logic — back off faster, detect the storm sooner, whatever. I didn't do that, because the underlying problem isn't a bad retry strategy, it's that `AudioUnitSetProperty` pinning and `AVAudioEngine`'s own device-change handling are fighting each other by design. A truly robust fix means replacing the pinning mechanism entirely (`AVCaptureSession` or raw AUHAL instead), which is a real project, not a patch. That's still on the list. It wasn't going to ship before the next person hit this.

So instead of trying to make the promise more reliable, I changed what the promise means. As of v1.4, a saved microphone pin is a **request**, not a guarantee — and the app will drop it mid-meeting the moment honoring it is doing more harm than good:

- **Circuit breaker.** More than 10 recovery cycles inside a rolling 60-second window means recovery itself has become the problem. Drop the pin immediately rather than let it keep retrying.
- **Post-start buffer verification.** `engine.isRunning == true` is not proof the engine is actually delivering audio — I'd already learned that the hard way with a different bug. If a pinned start reports "running" but delivers zero buffers within 5 seconds, that's a zombie: drop the pin and retry on the system default.
- **The existing last-resort escalation stays untouched.** If everything else fails, the app forces the built-in mic as a guaranteed-available device. That logic didn't need to change — it just needed to still be reachable after the two guards above.

The pin gets re-armed fresh at the start of every meeting, so a bad pin never permanently disables itself — it just yields for the one meeting where it's actively causing harm.

## Validating it

I reproduced the exact storm on purpose — same device configuration, same `-10868 FormatNotSupported` exceptions. The circuit breaker caught it at 11 cycles. Microphone recording was live 6 seconds into the meeting, on the system default, no user intervention required. Worst case went from "an entire meeting's voice track, gone" to "a few seconds of retries you'd never notice."

## What shipped after

v1.5 extended the same instinct to a related case: repeated Bluetooth reconnects used to permanently disable the pin until you re-enabled it by hand. Now it backs off for 120 seconds and tries again on its own. v1.7 tightened that recovery further after more real-world Bluetooth reconnect patterns showed up.

## The question I still haven't answered

Whisper resamples everything to 16kHz before transcribing, and Bluetooth's HFP profile already records at that same rate. Meetings recorded over AirPods before this feature ever existed transcribed just fine. So it's an open question whether pinning the built-in mic actually improves transcription accuracy at all, versus just sounding better to human ears in the moment. I haven't measured it properly yet — it's on the list before I invest more here.

If you hit something that looks like this — a meeting with one side of the conversation just missing, no error shown — [open an issue](https://github.com/mathguimaraes/routine-meeting/issues). The `processor.log` and app logs (introduced back in v1.1, partly because of exactly this kind of silent failure) will usually tell the real story.
