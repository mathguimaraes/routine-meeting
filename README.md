<div align="center">

<img src="icon.png" width="128" height="128" alt="Routine Meeting icon">

# Routine Meeting

**Meetings happen. Notes shouldn't require you to take them.**

[Download for macOS](https://github.com/mathguimaraes/routine-meeting/releases/latest) · Apple Silicon · macOS 13+

</div>

---

## The problem

You join a call, and the second it gets interesting you have to choose: pay attention, or write it down. Miss the meeting's start scrambling for a notes app. Forget to hit record. Get to Friday with six meetings' worth of decisions and action items living nowhere but your memory.

Most recording tools make this worse, not better — they need you to remember to press start, they dump raw audio to some server, and half of them can't tell your voice from everyone else's.

## What Routine Meeting does

Routine Meeting sits quietly in your menu bar and handles the whole thing without being asked:

- **Notices you're in a meeting and starts recording on its own — in *any* app.** It's not a Zoom/Meet/Teams integration with a fixed list of supported apps; it listens for the mic + system-audio pattern of an actual conversation. That means it works the same way for Google Meet, Zoom, Microsoft Teams, Webex, Slack huddles, Discord, FaceTime, WhatsApp calls, or a phone call relayed to your Mac — anything with two-way audio, no setup per app. No button to remember, no "oh no, was this being recorded" moment.
- **Transcribes it entirely on your Mac.** [WhisperKit](https://github.com/argmaxinc/WhisperKit) runs on the Apple Silicon Neural Engine — audio never leaves your machine.
- **Knows what you said vs. what everyone else said.** Mic and system audio are captured and split separately, so summaries and insights are attributed to the right person.
- **Turns the transcript into something useful** — a title, a bullet summary, action items, and (optionally) an honest read on how you performed in that specific conversation, whether it was a 1:1, a client call, or a design review.
- **Rolls it all up into a daily report** — what happened today, across every meeting, and what you still owe someone.

You bring your own [Gemini API key](https://aistudio.google.com/apikey) for the AI layer (the free tier comfortably covers personal use) — or skip the key entirely and run a local model on-device.

## Why it's built this way

- **App-agnostic by design.** Most meeting recorders only work with a couple of big-name apps because they integrate against each one's SDK. Routine Meeting instead captures at the system audio level — every app that makes sound on your Mac is fair game, so it doesn't matter what your team, your client, or your family standardized on.
- **Local-first.** Recording and transcription happen on your Mac regardless of whether you ever add an API key. The only thing that can leave your machine is a text transcript, and only if you turn cloud summaries on.
- **No accounts, no subscription.** It's a native app, not a SaaS wrapper. You own the DMG, you own your data.
- **Built for how meetings actually go.** False starts (music, a stray voice message) don't turn into phantom recordings; a dropped mic mid-call doesn't silently lose half your transcript.

## How Routine Meeting is different

Most meeting assistants, whether they use a visible bot (Fireflies, Otter) or "botless" capture (Fellow, Fathom), still send your recording and transcript to their servers for processing. Routine Meeting takes a different approach: everything happens on your Mac.

- **Nothing leaves your device.** Recording and transcription run entirely on-device. This is true even compared to tools that market themselves as "botless," since botless just means no visible participant joins the call, not that your data stays local. Unless you explicitly enable cloud AI summaries, Routine Meeting never uploads anything.
- **Works across every app, automatically.** Routine Meeting detects meetings by listening for the mic + system-audio pattern of a real conversation, not by joining as a participant or hooking into a specific app's API. That means Google Meet, Zoom, Teams, Webex, Slack huddles, Discord, FaceTime, or a phone call relayed through your Mac all work the same way, with zero per-app setup.
- **Bring your own key, or skip the cloud entirely.** AI summaries use your own Gemini API key (the free tier covers personal use), or you can run a fully local model with no key and no cloud calls at all.
- **No account, no subscription.** Routine Meeting is free and doesn't ask you to sign up for anything.

### What we don't have (yet)

To be upfront: Routine Meeting is a solo-built macOS app, not a funded platform. A few things Fireflies, Fellow, and similar tools offer that Routine Meeting doesn't:

- Cross-meeting search or a long-term searchable knowledge base (currently limited to a daily rollup)
- Integrations with CRMs, Slack, ATS tools, or dialers
- Enterprise compliance certifications (SOC 2, HIPAA, GDPR)
- Windows or mobile support

If you need any of those today, a platform like Fireflies or Fellow is probably the better fit, especially for regulated industries where those certifications matter. If what you want is something that never leaves your Mac and doesn't need a bot (or a cloud account) to work, that's exactly the gap Routine Meeting fills.

## Install

1. Download the latest `RoutineMeeting.dmg` from [Releases](https://github.com/mathguimaraes/routine-meeting/releases/latest).
2. Open the DMG and drag **Routine Meeting** into **Applications**.
3. Launch it. A short setup guide walks you through each permission — why it's needed, then the system prompt (Microphone, Screen Recording, Launch at Login, Accessibility, Notifications) — and lets you add a Gemini key or skip to on-device mode. The Screen Recording step is what captures other participants' audio and triggers the purple recording-indicator dot; that's expected and required.
4. Re-run this guide anytime from the menu bar icon → **Setup Guide…**.

Recordings older than 7 days are deleted automatically once they're transcribed (transcripts/summaries are kept forever) — configurable in Settings → Storage, with a manual "Free Up Space Now" button.

Routine Meeting checks for updates automatically (via [Sparkle](https://sparkle-project.org)) and notifies you in-app when a new version is ready.

## Privacy

Audio and transcripts stay on your Mac. Nothing is sent anywhere unless you turn on a cloud AI provider — and even then, only the transcript text goes out, never raw audio.

The app also sends one anonymous ping per day (a random ID with no meeting content, name, or email) so I can see rough usage. It's on by default; turn it off anytime in Settings → Privacy with no other change in behavior.

## Feedback / Issues

Menu bar icon → **Send Feedback…** in the app, or open an [issue](https://github.com/mathguimaraes/routine-meeting/issues) here.
