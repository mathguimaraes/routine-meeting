---
layout: post
title: "v1.9: Calendar titles, a Google Meet fix, and a lighter recorder"
description: "Optional calendar integration for real meeting titles and attendees, an End Meeting button, and fixes for Google Meet recordings splitting and calls ending early."
categories: [updates]
date: 2026-09-10
version: "1.9"
---

Routine Meeting 1.9 fixes two ways a recording could end up wrong, adds optional calendar integration, and makes recording lighter on your Mac.

**Fixes**

- **Google Meet no longer splits one call into several recordings.** The app was reading only the focused window's title to decide whether a meeting was still running, and that title changes every time you switch browser tabs. Switching tabs mid-call could look like the meeting ending and a new one starting.
- **A short silence no longer ends a meeting** while the call app still holds the microphone.

**New**

- **Calendar integration (optional).** Turn it on in Settings → Calendar and meetings get their real titles and attendees from your calendar instead of an AI-generated guess.
- **End Meeting button** on the live captions panel.
- **Live transcript preview inside the meeting view**, not only in the floating panel.

**Improved**

- Lower CPU and RAM use while recording, with a toggle to turn the live captions preview off entirely.

[Download v1.9](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.9) · [Full release notes](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.9)
