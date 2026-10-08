---
title: "Local and offline AI meeting notes on a Mac: Whisper, Ollama and 8 apps compared"
categories: [blog]
description: "What actually runs on your Mac for meeting transcription and summaries, what still needs internet once, and how to test it in airplane mode. Compared with dated sources."
date: 2026-10-06
last_modified_at: 2026-10-08
---

**Short answer:** you can record a meeting, transcribe it and write the summary entirely on a Mac, with Wi-Fi off. You need two local parts: a speech model that turns audio into text (Whisper-family models run well on Apple Silicon) and a small language model that turns the text into notes. The first run needs internet once, to download the models. After that, nothing has to leave the machine. Summaries from a small local model are weaker than a big cloud model, and that trade-off is the real decision.

*Disclosure: I build Routine Meeting, one of the apps below. Facts about the other apps come from their own sites and docs, checked on 2026-10-06 (Whisper Notes, Hapi, the Ollama route and the dictation note added 2026-10-08).*

## What runs where

A "local" meeting notes setup has three stages. Each can be local or cloud:

| Stage | Local version | Cloud version |
|---|---|---|
| Speech to text | Whisper-family model on the Mac's Neural Engine or GPU | Upload audio to a transcription API |
| Notes and summary | Small on-device language model | Send the transcript text to a hosted model |
| Storage | Files on your disk | Vendor servers |

"Offline" is the stricter claim: all three stages work with no network at all. Most apps that say "local" mean the first stage only. Always check the second.

<figure class="post-figure">
  <img src="{{ '/assets/blog/local-pipeline-offline.svg' | relative_url }}" alt="A fully local pipeline: record, transcribe with a Whisper-family model, summarize with a local model, keep files on disk" width="900" height="300" loading="lazy" style="width:100%;height:auto;display:block;border-radius:12px">
  <figcaption>A fully local pipeline needs no network once the models are downloaded.</figcaption>
</figure>

## Hardware: what you need

- **Apple Silicon** (M1 or later). Every on-device app below targets it, and so does Whisper acceleration.
- **RAM matters for summaries, not for transcription.** A local summary model takes a few gigabytes while it runs. On an 8 GB Mac, run only one model at a time; on 16 GB or more you have room to spare.
- **Disk:** models are downloaded once. Recordings can be large, so pick an app with automatic cleanup.

## The apps, step by step

### Routine Meeting (free)

Routine Meeting starts by itself when it hears the pattern of a real call, so you press nothing. It records your microphone and the system audio, then transcribes with WhisperKit on the Neural Engine, in two passes: your side and the other side, labeled separately. For summaries you choose a local model through MLX (Qwen2.5-3B, Llama-3.2-3B or Gemma-3-4B) or, optionally, your own Gemini key. The local path needs no key and makes no network call. Only one local model loads at a time, so an 8 GB Mac does not run out of memory.

Limits: closed source, speaker labels are you versus everyone else (not one name per person), no integrations, and local summaries are weaker than Gemini's.

### Biscotti (free, source-available)

Biscotti runs the whole pipeline locally: Whisper V3 Turbo, Pyannote for separating speakers, and a Gemma model for summaries, action items and titles. It records your mic and system audio with no bot. It needs macOS 15 or later and Apple Silicon, and recommends 16 GB of RAM. The license is PolyForm Perimeter, so the source is available but not open source in the usual sense.

### MacParakeet (free, GPL-3.0)

Open source, no account. Speech recognition runs on your Mac and the recorder separates you from everyone else. It writes audio to disk every second, so a crash does not lose the meeting. Summaries use the provider you configure (OpenAI, Anthropic, Ollama, LM Studio or OpenRouter), so they are local only if you choose Ollama or LM Studio. It needs macOS 14.2 or later and Apple Silicon.

<figure class="post-figure">
  <img src="{{ '/assets/blog/competitors/macparakeet-website-2026-10-08.jpg' | relative_url }}" alt="MacParakeet's meeting window showing a recording in progress with notes, transcript and mic and system audio meters" width="700" height="610" loading="lazy" style="width:100%;height:auto;display:block;border-radius:12px;max-width:560px;margin:0 auto;">
  <figcaption>Screenshot of MacParakeet's website, 2026-10-08. Image property of MacParakeet, shown for comparison.</figcaption>
</figure>

### Meetily (free community edition, MIT)

Open source and cross-platform (macOS, Windows, Linux). It transcribes with Whisper or Parakeet models and summarizes with Ollama locally, or a cloud provider if you prefer. Per its README, speaker identification is not in the free edition. Setup is more hands-on than a menu-bar app.

### Resonant

Resonant's site says its neural speech recognition runs on Apple Silicon and works in airplane mode and secure environments, on macOS 14 or later. Its page does not say whether summaries run locally, and I could not confirm price or speaker labels from the page I read, so I do not compare those.

### Quill (a note on a different approach)

Quill says audio is recorded and stored on your device and is not processed outside your computer, with no bot. It also offers calendar briefs, automations to tools like Slack and Notion, and a paid tier. I could not confirm from its page whether the summary step runs locally, so check that before relying on it for offline use.

### Whisper Notes ($14 once on Mac)

Per its site, Whisper Notes transcribes fully on the device with Whisper Large V3 Turbo and Parakeet V3, supports offline meeting recording on the direct-download Mac version, labels speakers on the device after the recording ends, and has no monthly minute cap. It needs Apple Silicon. Its summaries are not covered in the page I read.

### Hapi (from 79 EUR once for meetings)

Per its site, Hapi needs macOS 14 or later, says it is 100 percent local, auto-detects Zoom, Meet, Teams, Slack, WhatsApp and a few more apps from a list, and offers speaker labels and on-device AI summaries on its Local plan.

## Side by side

| | Routine Meeting | Biscotti | MacParakeet | Meetily | Resonant |
|---|---|---|---|---|---|
| Speech to text | Local (WhisperKit) | Local (Whisper V3 Turbo) | Local | Local (Whisper / Parakeet) | Local, per its site |
| Summary | Local MLX model, or Gemini key | Local (Gemma) | Your provider; local with Ollama / LM Studio | Ollama or cloud | Not stated |
| Works with Wi-Fi off | Yes, after models are downloaded | Yes, per its local claim | Yes if you use a local provider | Yes with Ollama | Yes, per its site |
| Speaker labels | You vs others | Per person | You vs others | Pro only | Not stated |
| Price | Free | Free | Free | Free; Pro paid | Not stated |
| Source | Closed | Source-available | GPL-3.0 | MIT | Not stated |
| Requirements | Apple Silicon | macOS 15+, 16 GB advised | macOS 14.2+ | macOS, Windows, Linux | macOS 14+, Apple Silicon |

Whisper Notes and Hapi are described above and are not in the table.

## The do-it-yourself route: Whisper plus Ollama

If you are comfortable in a terminal, you can build the same pipeline from parts. Many of the guides on this topic do exactly that: record the audio, transcribe it with a Whisper model, then pass the text to a local language model through Ollama.

1. **Record the call** with any app that saves your microphone and system audio.
2. **Transcribe it** with a Whisper-family model. MacWhisper, whisper.cpp or another local Whisper app all work. Check that the app you use runs the model on your Mac.
3. **Install Ollama**, download a model once (for example `ollama pull llama3.2`), then summarize the transcript (`ollama run llama3.2 "Summarize this meeting and list action items: ..."`). Ollama also offers cloud-hosted models, so pick a local model if you need to stay offline. Speed depends on your hardware, per Ollama's site.
4. **Run the offline test** below with Wi-Fi off.

This gives you full control and costs nothing, but you do the recording, copying and prompting by hand. An app removes those steps. Meetily, covered above, wraps the same Whisper plus Ollama idea in one app.

## Dictation apps are not meeting recorders

Searches for "offline speech to text for Mac" mostly return dictation and file transcription apps such as Superwhisper, TypeWhisper and MacWhisper. Per their own descriptions, dictation apps turn your voice into text in any text field, and file transcribers convert recordings you already have. Neither starts by itself when a call begins. If you want a call recorded and summarized without pressing anything, use a meeting recorder from the list above.

<figure class="post-figure">
  <img src="{{ '/screenshots/app-main.webp' | relative_url }}" alt="Routine Meeting main window: meeting list, weekly stats and the Task Radar" width="1577" height="997" loading="lazy" style="width:100%;height:auto;display:block;border-radius:12px">
  <figcaption>Routine Meeting's main window on a Mac.</figcaption>
</figure>

## Setup, step by step (Routine Meeting)

1. Install the app and open the setup guide. It explains each permission before it asks.
2. Allow Microphone, then Screen and System Audio Recording. The second name sounds scary, but only audio is captured, never video or screen content. macOS will show its purple recording indicator while recording.
3. Leave Launch at Login on, so it is running after a restart.
4. At the last step, skip the Gemini key and choose the on-device model.
5. Let the first model download finish while you are online. This is the only step that needs internet.
6. Join a call. Detection starts recording after a short delay, and stops when the call ends.

## The offline test (do this with any app)

Do not trust the label. Test it:

1. With internet on, install the app, complete setup and let every model download.
2. Turn Wi-Fi off, or enable Airplane Mode. Confirm the menu bar shows no connection.
3. Record a short call or play a recorded conversation through the speakers while talking.
4. Check that recording starts, the transcript appears, and the summary appears.
5. If any step fails or hangs, that step needs the network.

What always needs internet: downloading models, app updates, and any cloud summary you turn on. What should not: recording, transcription and a local summary.

## Local summaries versus Gemini: the trade-off

A small on-device model is private and works anywhere, but it is less reliable on long meetings, many speakers and subtle action items. A large cloud model writes better notes, at the cost of sending the transcript text (never the audio) to a provider. A reasonable middle path: use the local model for sensitive meetings and a cloud key for routine ones, and switch per need.

## FAQ

**Can a Mac do meeting transcription offline?** Yes, with a local speech model. The models must be downloaded first.

**Do I need an internet connection for summaries?** Not with a local model. Cloud summaries need one.

**Is local transcription accurate?** Whisper-family models are strong on clear speech. Accuracy drops with overlapping talk, noise and accents, and a larger model is slower.

**Will it work on an 8 GB Mac?** Transcription usually does. Run one summary model at a time and close other heavy apps.

**Does local mean no consent needed?** No. Recording laws still apply. Tell participants before recording.

## Sources (checked 2026-10-06, additions 2026-10-08)

- Biscotti: [github.com/scosman/Biscotti](https://github.com/scosman/Biscotti)
- MacParakeet: [macparakeet.com/meetings](https://macparakeet.com/meetings)
- Meetily: [github.com/Zackriya-Solutions/meetily](https://github.com/Zackriya-Solutions/meetily)
- Resonant: [onresonant.com/resources](https://onresonant.com/resources)
- Quill: [quillmeetings.com](https://quillmeetings.com)
- Whisper Notes: [whispernotes.app/whisper-notes-vs-otter-ai](https://whispernotes.app/whisper-notes-vs-otter-ai)
- Hapi: [speakhapi.com](https://speakhapi.com)
- Ollama: [ollama.com](https://ollama.com)
