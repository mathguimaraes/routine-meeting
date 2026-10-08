---
title: "Private meeting transcription on Mac: where your audio actually goes (and 9 apps compared)"
categories: [blog]
description: "Which Mac meeting transcribers keep audio on your device, which send text or audio to the cloud, and what each one costs. Compared with dated sources."
date: 2026-10-06
last_modified_at: 2026-10-08
---

**Short answer:** for private meeting transcription on a Mac, pick an app that records and transcribes on your device, with no bot in the call and no account. MacWhisper, MacParakeet, Biscotti, Meetily, Whisper Notes, Hapi and Routine Meeting all do that, and Apple Notes can record and transcribe for free if you only need it now and then. Cloud-first tools such as Granola send your meeting audio to third-party transcription providers, even though they do not keep the recording. The real differences between the on-device apps are price, how much setup you need, whether the AI summary stays local, and how mature each app is.

*Disclosure: I build Routine Meeting, one of the apps below. Everything about the other apps comes from their own websites and docs, checked on 2026-10-06 (Apple Notes, Whisper Notes, Hapi and the regulated-work section added 2026-10-08). If something has changed, tell me and I will fix it.*

## What "private" actually means for a meeting recorder

"Private" is used loosely. A meeting passes through four steps, and each one can be local or not:

1. **Capture.** A bot joins the call as a participant (cloud), or the app records your Mac's audio (local).
2. **Transcription.** Speech to text runs on your Mac, or the audio is uploaded to a provider.
3. **Summary.** An AI turns the transcript into notes, either with a local model or by sending the transcript text to a cloud model.
4. **Storage.** Recordings and notes live on your disk, or on the vendor's servers.

A tool can be bot-free and still upload your audio in step 2. So ask four questions of any app: does a bot join, where is the speech recognized, where does the summary run, and where is everything stored.

## The apps, step by step

### MacWhisper (Pro: 64 EUR, one time)

MacWhisper started as a file transcriber and now also records meetings. Its site says it records online meetings with no bots joining, and lists automatic meeting start and end detection for Zoom, Teams, Webex, Skype, Chime, Discord and more. Transcription uses local models. You can add AI summaries by connecting your own provider keys, or a local model through Ollama or LM Studio. Meeting recording is listed under the Pro plan; there is a free tier for file transcription.

Good for: people who also transcribe lots of audio files, podcasts and dictation, and want one mature tool for all of it.

Limits to know: its docs describe meeting recording as a beta, and say all participants are grouped as one speaker for now. The docs also recommend manual recording for critical meetings, because of possible data loss in the beta. Meeting recording needs the standalone version, not the Mac App Store one.

### MacParakeet (free, GPL-3.0)

MacParakeet is free, open source under GPL-3.0, and needs no account or subscription. Speech recognition runs on your Mac. Its meeting recorder separates you from everyone else, fragments audio to disk every second so a crash does not lose the recording, and has no time limit. Summaries go through the "Ask" feature with the AI provider you choose (OpenAI, Anthropic, Ollama, LM Studio, OpenRouter), so only transcript text leaves the Mac, and only if you pick a cloud provider.

Good for: people who want open source and a recorder that is built to survive crashes.

Limits to know: it needs macOS 14.2 or later and Apple Silicon. Summaries are not built in; you wire up your own provider.

### Biscotti (free, source-available)

Biscotti records your mic and your Mac's system audio, with no bot, and runs everything locally: Whisper V3 Turbo for transcription, Pyannote for separating speakers, and a Gemma model for summaries, action items and titles. It uses calendar data to help name speakers. It is free with no account.

Good for: people who want the most complete fully local pipeline, including per-person speaker separation and local summaries, with nothing to configure.

Limits to know: the license is PolyForm Perimeter, so the source is available but it is not open source in the usual sense. It needs macOS 15 or later, Apple Silicon, and recommends 16 GB of RAM because the summary model is large.

### Meetily (free community edition, MIT)

Meetily is open source (MIT) and runs on macOS, Windows and Linux. It transcribes with Whisper or Parakeet models and summarizes locally through Ollama, or with a cloud provider if you prefer. Its README says all processing happens locally.

Good for: people on more than one operating system, or who want to inspect and modify the code.

Limits to know: speaker identification is not in the free community edition; it is listed as a Pro feature, along with custom templates and calendar integration. Setup is more hands-on than a menu-bar app.

### Granola (the cloud-assisted comparison)

Granola is popular, bot-free, and polished, so people often ask whether it counts as private. Its security page says it does not store meeting audio and transcribes in real time on the desktop. It also says it uses third-party transcription providers (it names Deepgram and AssemblyAI) and AI providers (OpenAI and Anthropic) for summaries. Notes are stored in its US-hosted AWS environment, encrypted at rest and in transit. The company is SOC 2 Type 2 audited. It states that third parties may not train on your data, but that Granola itself trains on anonymized data, with an opt-out for individuals.

Good for: teams that want a hosted, audited product with sharing and integrations.

Limits to know for privacy: your audio goes to external providers for transcription, and notes live on its servers. If your rule is "audio never leaves my Mac", it does not meet it. That is a legitimate choice for many teams; just make it knowingly.

### Apple Notes (free, built in)

Apple Notes can record audio inside a note and show a live transcript. Per Apple's support page, transcription needs a Mac with an M1 chip or later, works in English (several regional variants), Spanish, Portuguese, Italian, French, German, Japanese, Korean and Chinese, and Apple Intelligence can write a summary. The page describes recording through the Mac's audio input and does not mention system audio, so on a call it will hear you, and the other side only if they come through your microphone. It does not say whether transcription runs on the device, so check that before relying on it for private work. It has no meeting detection, no speaker labels and no bot.

Good for: occasional recordings where you want zero extra software.

### Whisper Notes ($14 once on Mac)

Per its site, Whisper Notes transcribes fully on the device with Whisper Large V3 Turbo and Parakeet V3, supports offline meeting recording on the direct-download Mac version, labels speakers on the device after the recording ends, and has no monthly minute cap. It needs Apple Silicon.

### Hapi (from 79 EUR once for meetings)

Per its site, Hapi is a macOS 14 or later app that says it is 100 percent local, auto-detects Zoom, Meet, Teams, Slack, WhatsApp and a few more apps from a list, and offers speaker labels and on-device summaries on its Local plan. Its free tier covers voice notes only.

## Where Routine Meeting fits

Routine Meeting is a menu-bar app that starts by itself. Instead of integrating with Zoom or Teams, it notices the pattern of a real two-way conversation (your microphone active plus audio playing from another app), so it also catches Slack huddles, Discord, FaceTime or a call relayed to the Mac, with no per-app setup.

- **Capture:** your microphone plus system audio through macOS ScreenCaptureKit. No bot, no video, audio only. macOS shows its purple recording indicator while it records; that is the operating system and cannot be hidden.
- **Transcription:** WhisperKit on your Mac's Neural Engine. Your side and the other side are transcribed separately and labeled "What you said" and "What others said".
- **Summaries:** optional. You can use your own Gemini API key (only the transcript text is sent, never audio), or a fully local model through MLX with no key and no network call.
- **Storage:** everything stays on your Mac. Old recordings are cleaned up after a number of days you choose, but only once a transcript exists. Transcripts and summaries are kept.
- **Cost:** free, no account.

Limits, stated plainly:

- It is **closed source**. If you need to audit the code, choose MacParakeet or Meetily.
- Speaker labels are **you versus everyone else**, not a name per person. Biscotti does separate individual speakers.
- No integrations (CRM, Slack, Notion) and no SOC 2 report.
- If you turn on cloud summaries with a Gemini key, transcript text goes to Google. Use the local model if that is not acceptable.

## Healthcare, legal and other regulated work

People searching for private transcription often work with patient, client or student information. Two points matter before you pick a tool.

**Local is not the same as compliant.** An app that keeps audio on your Mac means no vendor holds your recordings, which removes a large risk. It does not by itself satisfy a rule such as HIPAA or a law firm's confidentiality policy. Your disk encryption, backups, retention and who can open the Mac still count. Routine Meeting has no SOC 2 report and does not offer a business associate agreement. If your organization needs either, a hosted vendor with those documents (Granola and Fellow publish SOC 2 Type 2 information, and Otter states HIPAA compliance) may be the compliant route, even though audio then leaves your Mac.

**Check that every feature is local.** Some apps keep transcription on the device and send audio or text elsewhere for speaker labels or summaries. Test each step with Wi-Fi off, as in the checklist below, and ask your compliance contact before recording anything covered by a rule.

This is not legal advice.

## Side by side

| | Routine Meeting | MacWhisper | MacParakeet | Biscotti | Meetily | Granola |
|---|---|---|---|---|---|---|
| Bot joins the call | No | No | No | No | No | No |
| Speech recognition | On your Mac | On your Mac (local models) | On your Mac | On your Mac | On your Mac | Third-party providers |
| Summary | Local model, or your Gemini key | Your keys, or Ollama / LM Studio | Your chosen provider | Local (Gemma) | Ollama, or cloud | Cloud (OpenAI, Anthropic) |
| Speaker labels | You vs others | One speaker (beta docs) | You vs others | Per person | Pro only | Not checked |
| Starts automatically | Yes, any app | Yes, listed apps | Not checked | Not checked | Not checked | Calendar based, not checked |
| Price | Free | Free tier; Pro 64 EUR once | Free | Free | Free; Pro paid | Not checked |
| Source | Closed | Closed | GPL-3.0 | Source-available | MIT | Closed |
| Compliance | None | Not stated | Not stated | Not stated | Not stated | SOC 2 Type 2 |

"Not checked" means I did not verify it on the vendor's site and will not guess. Apple Notes, Whisper Notes and Hapi are described above and are not in the table.

## Which one should you pick?

- **You want the most local, no setup:** Biscotti, if your Mac is on macOS 15 with enough RAM. Otherwise Routine Meeting with the local model.
- **You want open source you can audit:** MacParakeet (GPL-3.0) or Meetily (MIT).
- **You also transcribe lots of files and dictate:** MacWhisper.
- **You want it to start with every call, in any app, without picking apps from a list:** Routine Meeting.
- **You need sharing, integrations or a SOC 2 report:** a hosted tool such as Granola, accepting that audio goes to third-party providers.

## A quick checklist before you trust any "private" claim

1. Does it say where speech recognition runs? "On-device" and "local" should be stated for transcription, not just for storage.
2. What does the AI summary send out, and can you turn it off or make it local?
3. Can you test it with Wi-Fi off? A local transcriber still works in airplane mode.
4. Is the license and the source something you can check?
5. What does it do if the app crashes mid-meeting?
6. Is every feature local? Test transcription, speaker labels and summaries one by one with Wi-Fi off.

## Recording consent

Local does not change the law. Many places require telling the other people that you are recording, and some require their consent. Tell participants before you record, whichever app you use.

## FAQ

**Is it legal to record a meeting on my Mac?** It depends on where you and the other participants are. Many jurisdictions require notice or consent from everyone. Ask first.

**Does a no-bot app mean nothing leaves my Mac?** No. Bot-free only describes how the audio is captured. Check where transcription and summaries run.

**Can these apps work offline?** Apps that transcribe on your device can transcribe without internet. Summaries need a local model to be fully offline.

**Do I need a powerful Mac?** Apple Silicon is the common requirement. Local summary models are the heavy part, so more RAM helps.

**Is Apple Notes good enough?** For an occasional recording, possibly. Per Apple's page it records through the Mac's audio input, so it may not capture the other side of a call, and it does not say where transcription runs.

**Is local transcription HIPAA compliant?** Not automatically. Local processing keeps audio off vendor servers, but compliance depends on your organization's rules, your device security and any agreements you need. Ask your compliance contact.

**Is Routine Meeting free?** Yes, with no account.

## Sources (checked 2026-10-06, additions 2026-10-08)

- MacWhisper: macwhisper.com and docs.macwhisper.com (record meetings article)
- MacParakeet: macparakeet.com/meetings
- Biscotti: github.com/scosman/Biscotti
- Meetily: github.com/Zackriya-Solutions/meetily
- Granola: granola.ai/security
- Apple Notes: support.apple.com/guide/notes/record-and-transcribe-audio-apdb5106e334/mac
- Whisper Notes: whispernotes.app/whisper-notes-vs-otter-ai
- Hapi: speakhapi.com
