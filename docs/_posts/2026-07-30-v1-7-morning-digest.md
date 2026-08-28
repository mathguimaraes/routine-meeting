---
layout: post
title: "v1.7: A morning digest, and a transcription hang finally tracked down"
description: "Yesterday's recap now lands as a notification each morning, plus a fix for transcriptions that hung indefinitely on iCloud-synced Macs."
categories: [updates]
date: 2026-07-30
version: "1.7"
---

The headline fix in 1.7 is one that took a while to pin down: transcription could hang indefinitely for some users, and the root cause turned out to be where the WhisperKit and local-LLM model cache lived — inside `~/Documents`, which iCloud Drive can partially sync and evict files from on demand, including mid-transcription. The cache now lives in Application Support instead, outside iCloud's sync scope entirely.

Alongside that:

- **Morning digest notification.** A summary of yesterday's meetings and open tasks now arrives as a notification a few minutes after your Mac wakes, instead of only showing up if you happen to open the app.
- **Daily Report now defaults to yesterday.** The home screen's report opens on yesterday's recap instead of today's mostly-empty one, since that's almost always what you actually want first thing in the morning.
- **Updated app icon rendering for macOS 26 Tahoe**, using Apple's new layered `.icon` format for proper full-bleed display with the Liquid Glass treatment.
- **Force Microphone Input recovery improved** after repeated Bluetooth reconnects — a continuation of the fail-open work from v1.4–v1.5 (see the [mic pin postmortem](/routine-meeting/blog/mic-pin-recovery-storm/) if you want the full story there).
- **Anonymous daily usage ping**, toggleable in Settings → Privacy. It's a random ID with no meeting content, name, or email attached — just enough to see rough usage in aggregate.

[Download v1.7](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.7) · [Full release notes](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.7)
