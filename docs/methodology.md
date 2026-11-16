---
layout: default
title: How we research and correct our comparisons
seo_title: Methodology and corrections
description: How the comparison posts on this site are researched, what counts as a source, what we do not test, and a public log of corrections.
permalink: /methodology/
---

<article class="post" markdown="1">
<div class="section-inner post-inner" markdown="1">
<div class="post-body" markdown="1">

# How we research and correct our comparisons

*Last updated 2026-10-26.*

Routine Meeting is a free Mac meeting recorder, and I build it. The comparison posts on this site compare it with other apps, including paid ones that do some things better. This page says how those posts are made, so you can judge how far to trust them, and it keeps a public log of mistakes.

## Who writes the posts

I build Routine Meeting, and every comparison post says so in its first lines. Where a competitor is better for a job, the post says that too, and each post lists what Routine Meeting does not do.

## What counts as a source

- **Facts about another app** come from that app's own pages: its website, pricing page, security page, documentation and GitHub repository. Each post ends with a list of those sources and the dates they were read.
- **Facts about Routine Meeting** come from its own behavior and design, which I know first-hand.
- **News and legal claims** are attributed to the outlet that reported them and described as allegations when they are allegations. I do not read court filings unless a post says I did.
- **Search results** (for example, which pages appear for a query) are dated when they are cited.

## What we do not do

- **We do not install and test competing apps.** Statements such as "starts automatically" or "labels speakers" are what the vendor's own pages say. When a page is unclear, the post says "not stated" or "not checked" instead of guessing. A table cell reading "Not checked" means exactly that.
- **We do not take paid placement.** No one pays to be listed or ranked in these posts.
- **We do not rank ourselves first by default.** Recommendations are written per situation ("you want open source: Meetily or Muesli"), and the lists include the cases where another app is the better choice.

## Dates and changes

Prices, platforms and features change. Each post carries a "checked" date next to its sources, and a fact is only as current as that date. When a vendor changes something, the post is updated and the change is recorded below.

## Screenshots

Screenshots of other companies' websites are dated, credited as the property of their owners and used only for comparison. Diagrams are drawn from the same dated sources as the text.

## Recording and consent

Recording laws depend on where you and the others are, and many places require everyone's consent. The posts say this because it applies to every tool they compare, including ours. None of it is legal advice.

## Report a mistake

If something about your app or about Routine Meeting is wrong, tell me through [GitHub issues](https://github.com/mathguimaraes/routine-meeting/issues), with a link to the source if you have one. I will check it against the vendor's own page, fix the post and add a line to the log below, crediting you if you want to be named.

## Corrections log

| Date | Page | What was wrong | What changed |
|---|---|---|---|
| 2026-10-21 | Homepage | The "what it does not do" list said the app has no cross-meeting search and offers only a daily rollup. Keyword search across meetings shipped in v1.8 (2026-08-10). | The line now says team sharing is missing and that keyword search across your own meetings is built in. |
| 2026-11-16 | Homepage, READMEs and comparison posts | Several pages said Routine Meeting needs macOS 13 or later. The app has required macOS 14.2 since 1.12.3. | The requirement now reads macOS 14.2 or later. |
| 2026-11-16 | Comparison posts and glossary | The posts said Routine Meeting transcribes with WhisperKit, that its main window shows a "What you're discussing" home page, and (in one post) that it has no dictation. Version 1.13 (2026-11-16) switched meeting transcription to Parakeet v3, kept Whisper as an option, retired that home page and added a beta dictation mode. | Each statement about Routine Meeting now matches version 1.13. Statements about other apps are unchanged. The glossary has new Parakeet and Dictation entries. |
| 2026-11-16 | Comparison posts, glossary and READMEs | Posts said system audio is captured through ScreenCaptureKit, that recording starts after about ten seconds, that the app has no Dock icon, that search covers insights, and that it writes a daily recap and Insights. System audio uses a Core Audio tap (macOS 14.2+), the start delay defaults to 5 seconds once audio from another app is heard, a Dock icon shows while a window is open, search covers title, attendees, summary and transcript, and Insights and the daily report are gone since 1.11. | Each statement now matches the app. Release posts for 1.7, 1.8 and 1.10 carry an update note. |
| 2026-11-16 | Local AI post | The post implied an 8 GB Mac simply runs one model at a time. | It now says summaries wait for spare memory and can be slower on 8 GB. |

This log lists every correction since the comparison posts started on 2026-10-06, including small ones.

</div>
</div>
</article>
