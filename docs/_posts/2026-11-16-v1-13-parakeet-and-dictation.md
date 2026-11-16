---
layout: post
title: "v1.13: Parakeet transcription, dictation with the Fn key, and gentler on memory"
description: "Meetings are transcribed with Parakeet v3, dictation arrives in beta, on-device summaries wait for spare memory, and the AI home page is retired."
categories: [updates]
date: 2026-11-16
version: "1.13.0"
---

Routine Meeting 1.13 is about speed, and about being easier on a Mac with 8 GB of memory.

**Faster transcription with Parakeet v3**

Meetings are now transcribed with NVIDIA's Parakeet v3 model, running on your Mac. In our tests an hour-long call takes a few minutes. Whisper is still there: choose it in Settings under Speech engines. Parakeet's model files (about 0.6 GB) download the first time you transcribe a meeting, and if Parakeet cannot load, Routine Meeting falls back to Whisper. Parakeet can drift between languages in calls that mix Spanish, Portuguese and English, so compare the two before relying on it for those.

**Dictation, in beta**

Hold Fn in any app, speak, and release. Your words are transcribed on your Mac and pasted where your cursor is. Set it up from the menu bar item "Set Up Dictation Shortcut…". It needs Input Monitoring and Accessibility permissions, and the app asks for them only then. You can choose which microphone dictation uses in Settings, and your personal dictionary applies.

An optional AI polish step (off by default) uses Apple's on-device model to remove filler words and fix punctuation. It is skipped for short phrases and when your Mac is short of memory, so it never slows dictation down.

**Gentler on memory and heat**

- On-device AI summaries now wait until your Mac has spare memory. They never run while you are recording or while a meeting is being transcribed. The transcript itself is never delayed.
- Microphone audio is saved at 16 kHz mono, about six times smaller than before. Speech recognition used that resolution already.
- Dictation stays quiet while a meeting is recording, and meetings are transcribed one at a time.

**Fixes**

- Fixed a freeze that could happen when a microphone, such as AirPods, disconnected in the middle of a meeting. If the chosen microphone drops, recording now continues on the built-in one.
- Fixed high CPU use on the home screen after a meeting.

**Removed**

The AI-written "What you're discussing" home page is gone. The home screen now shows today's and this week's stats and your recent meetings, with a shortcut to your personal dictionary. The old topics file stays in your Application Support folder and is no longer used.

[Download v1.13.0](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.13.0) · [Full release notes](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.13.0)
