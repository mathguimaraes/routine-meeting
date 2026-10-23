---
layout: post
title: "v1.10: Task Radar review, calendar Join, and no more live transcript preview"
description: "Approve or reject detected tasks, add your own, join calendar events from the menu bar, and a recording timer. The live transcript preview is gone because it cost 30–40% CPU."
categories: [updates]
date: 2026-10-02
version: "1.10.0"
---

Routine Meeting 1.10 is mostly about Task Radar, plus calendar and recording changes.

**Task Radar**

- Add tasks yourself with the + button.
- Newly detected tasks now wait for your approval before joining the list. You can Approve All, Reject All, or reject by owner or category.
- After each meeting a review banner shows what was resolved, updated or added, with one-click Undo.
- It tracks only your tasks, not every attendee's.
- Your manual edits to an owner, text or due date are never overwritten by automatic updates.
- Edit tasks inline, exclude them (with undo), view Done and Excluded, sort and combine filters, and copy a task or a whole category.

**Recording**

- A live recording timer in the menu bar and the app window.
- **The real-time transcript preview is removed.** It cost 30–40% CPU while recording. The floating window is now a small End / dismiss pill.
- Ending a meeting manually no longer lets auto-detection restart recording for 3 minutes.

**Calendar and setup**

- Upcoming calendar events appear in the menu bar with a one-click Join.
- The Setup Guide now walks you through getting a Gemini key, picking it up from the clipboard and testing it automatically.
- A clear message when Calendar access is blocked, with a shortcut to the privacy settings.

**Fixes**

- Resizing the window no longer overlaps the sidebar.
- There is a single Settings window.
- Gemini requests retry on the next model when one rejects them.
- Removed the "Yesterday's recap" morning notification.

[Download v1.10.0](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.10.0) · [Full release notes](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.10.0)
