---
layout: default
title: Privacy Policy
description: What Routine Meeting stores, what it sends, and how to turn it off.
permalink: /privacy/
---

<article class="post" markdown="1">
<div class="section-inner post-inner" markdown="1">
<div class="post-body" markdown="1">

# Privacy Policy

Last updated: September 20, 2026

Routine Meeting is a Mac app that records and transcribes your meetings on
your own computer. This page explains what stays on your Mac, what the app
sends over the internet, and how to turn it off.

## The short version

- Your audio and transcripts stay on your Mac.
- No account is needed to use the app.
- Audio is never uploaded anywhere.
- Text leaves your Mac only if you turn on a cloud AI provider with your own
  key, and then only the transcript text goes to that provider.
- The app sends one small anonymous ping per day. You can turn it off.

## What stays on your Mac

- Recordings (microphone and system audio), transcripts, summaries, action
  items, insights and daily recaps.
- Your settings and any API keys you enter.
- By default, the raw audio of a meeting is deleted 7 days after it has been
  transcribed. You can change this in Settings, or delete meetings yourself.
  Transcripts and summaries are kept until you delete them.

The app does not capture video or screen content. Screen and system audio
recording permission is used only to hear the other participants' audio.

## Permissions the app asks for

| Permission | Why |
|---|---|
| Microphone | To detect and record your side of a meeting. |
| Screen and system audio recording | To record the other participants' audio. Audio only. |
| Notifications | To tell you when a transcript or daily recap is ready. |
| Accessibility (optional) | To paste your meeting prompt into an AI assistant, and to notice when you move straight from one meeting into another. |
| Automation for Google Chrome (optional) | To check whether your meeting tab is still open. |
| Calendar (optional, only if you turn it on in Settings) | To name meetings after the real event and identify attendees. |

## What the app sends over the internet

| What | When | What is sent |
|---|---|---|
| Anonymous usage ping | Once a day, on by default | A random ID created on your Mac and the app version. No meeting content, name or email. As with any web request, the server can see your IP address. |
| Update check | Periodically | A request to GitHub for the update file. The app does not send your data. |
| Model downloads | When you choose or first use a transcription model | A download of the model files from the model host. |
| Cloud AI provider (optional) | Only if you turn it on | The transcript text is sent to the provider you choose (for example Google Gemini) using your own API key. Their privacy policy applies to that text. Audio is never sent. |
| Team sign-in (optional) | Only if you click "Sign in with Google" in Settings | Your Google sign-in with the sign-in service used for the Team feature. This feature is not finished. |

If you use a local model for summaries, no transcript text leaves your Mac.

## How to turn things off

- Anonymous ping: Settings, Privacy, turn off the anonymous daily usage ping.
  Nothing else in the app changes.
- Cloud AI: leave it off, or remove your API key in Settings.
- Delete data: delete a meeting in the app, or delete the app's data folder
  in your Mac's Application Support folder.

## What we do not do

- We do not sell or share your data.
- We do not show ads.
- We do not read your meetings. They are on your computer, not ours.

## Recording consent

Laws about recording conversations differ by country and state, and many
require the consent of everyone on the call. You are responsible for
telling participants and following the rules where you and they are.

## Changes and contact

If this policy changes, the date at the top will change. Questions or
requests: open an issue at
<https://github.com/mathguimaraes/routine-meeting/issues>.

</div>
</div>
</article>
