---
layout: default
title: Glossary of Mac meeting recording and transcription terms
seo_title: Glossary of meeting transcription terms
description: "Plain definitions of the terms used when comparing Mac meeting recorders: on-device transcription, botless recording, system audio capture, speaker labels, notarization and more."
permalink: /glossary/
---

<article class="post" markdown="1">
<div class="section-inner post-inner" markdown="1">
<div class="post-body" markdown="1">

# Glossary of Mac meeting recording and transcription terms

*Last updated 2026-10-27.*

Short definitions of the terms that come up when you compare meeting recorders on a Mac. I build Routine Meeting, so where a term describes how it works, the definition says so.

## Recording

**Meeting bot.** A participant that joins your call as a named attendee to record it, usually from a vendor's cloud. Everyone on the call sees it and the audio is processed on the vendor's servers. See [bot, no bot and on-device compared](/routine-meeting/blog/meeting-bot-vs-no-bot-vs-on-device/).

**Botless recording.** Recording from your own computer's audio instead of sending a bot into the call. Nobody sees an extra attendee. It does not remove the need to tell people you are recording where consent is required.

**System audio capture.** Recording the sound your Mac is playing, which is where the other people on a call are heard. On macOS this uses Apple's ScreenCaptureKit, and the system shows a purple recording indicator while it runs. Video and screen content are not part of the audio capture.

**Microphone track.** The recording of your own voice from the mic, kept separate from system audio. Keeping the two apart is what lets an app label "you" and "everyone else" without guessing.

**App-agnostic detection.** Noticing that a call is happening from the pattern of microphone and system audio, instead of integrating with Zoom, Meet or Teams one by one. Routine Meeting detects meetings this way, so Slack huddles, FaceTime and Discord work too. See [how to record those](/routine-meeting/blog/transcribe-slack-huddles-facetime-discord-mac/).

**Menu-bar app.** An app that lives in the macOS menu bar with no Dock icon while it runs. Routine Meeting is one.

## Transcription and speakers

**On-device transcription.** Turning speech into text on your own Mac, so the audio is not uploaded. Quality and speed depend on the model and the chip. Routine Meeting uses WhisperKit on Apple Silicon.

**Whisper.** An open speech recognition model from OpenAI. Many Mac apps run it locally in some form.

**WhisperKit.** An open-source framework that runs Whisper models on Apple devices using the Neural Engine. It is what Routine Meeting uses for transcription.

**Apple Silicon.** Apple's own Mac chips (M1 and later). Local transcription and local summaries run much faster on them than on Intel Macs, and Routine Meeting requires one.

**Speaker labels.** Marking who said each line. There are two common methods. Separating the mic track from system audio tells you "you" versus "others". Diarization tries to tell several voices apart inside one track. Routine Meeting does the first: it transcribes your mic and the system audio separately and labels the two sections. It does not name each remote participant.

**Diarization.** Splitting one audio track into "speaker 1, speaker 2" by voice. It is harder than separating tracks and can mix people up.

**Transcript.** The full text of what was said. A summary is built from it, so errors in the transcript carry into the summary.

## Summaries and AI

**On-device summary.** A summary written by a language model running on your Mac. In Routine Meeting it defaults to Apple's built-in model, and nothing leaves the Mac.

**Cloud summary.** A summary written by a model on a vendor's servers. In Routine Meeting this is optional and uses your own Gemini key, so the transcript text (not the audio) goes to Google when you turn it on.

**Bring your own key (BYOK).** You supply your own API key for a cloud AI service instead of paying the app maker for access. Usage is billed by that provider to you, and some providers have a free tier.

**Local LLM.** A language model that runs on your own computer. It trades some writing quality for privacy and no per-use cost.

## Distribution and trust

**Signed and notarized.** Apple's process for apps distributed outside the Mac App Store. Signing identifies the developer, and notarization is an automated Apple check for malicious code. A notarized app opens without the "unidentified developer" warning. Routine Meeting's current release is signed and notarized.

**Closed source.** The code is not public. You can inspect the app's behavior, permissions and network traffic, but not its source. Routine Meeting is closed source. Some alternatives are open source, and the [comparison posts](/routine-meeting/blog/meetily-alternative-mac/) say which.

**Public beta.** Released to everyone and still changing. Routine Meeting is in public beta. See the [version history](/routine-meeting/updates/).

**Retention.** How long recordings are kept. Routine Meeting deletes the audio of transcribed meetings after 7 days by default and keeps transcripts and summaries. The setting is in Settings, Storage.

## Related pages

- [How we research and correct our comparisons](/routine-meeting/methodology/)
- [Private meeting transcription on a Mac](/routine-meeting/blog/private-meeting-transcription-mac/)
- [How to transcribe a meeting on a Mac](/routine-meeting/blog/how-to-transcribe-meetings-on-mac/)

</div>
</div>
</article>
