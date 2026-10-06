---
title: "Otter alternative for Mac: local, no account, no minute caps (and how Otter's Mac app really works)"
categories: [blog]
description: "Otter now has a bot-free Mac app, so the real differences are where your audio goes, accounts, minute caps and price. Otter compared with Routine Meeting and five other Mac options, with dated sources."
date: 2026-10-06
---

**Short answer:** Otter is a strong choice for teams that want shared notes, integrations and a compliance report. If you are one person on a Mac who wants meeting transcription that stays on your machine, with no account and no minute cap, a local app is the better fit. Routine Meeting, MacWhisper, Biscotti, MacParakeet and echo99 all record and transcribe on the Mac. The common claim that "Otter makes a bot join your call" is out of date: Otter has had a bot-free desktop app for Mac since late 2025. The differences that remain are where audio is processed and stored, whether you need an account, and what you pay.

*Disclosure: I build Routine Meeting, one of the options below. Facts about Otter and the other apps come from their own websites and help pages, checked on 2026-10-06. Otter's Mac product page sits behind a sign-in wall, so for the Mac app I used its help center, its desktop pages and its launch post.*

## How Otter works on a Mac today

Otter offers two ways to capture a meeting, and many comparison pages only mention the first:

1. **The bot.** Otter's notetaker joins your Zoom, Teams or Google Meet call as a participant.
2. **The desktop app.** Announced on October 7, 2025 for Mac and Windows. Per Otter's help article, it records audio without a bot joining. It needs macOS 12.3 or later, plus two permissions: Microphone, and Screen and Audio Recording. It can detect meetings on Zoom, Teams, Google Meet and Slack huddles, or you press Record yourself, and it also covers in-person conversations. If it hears no conversation for 10 minutes it stops recording after 15 seconds unless you tell it to continue.

Otter's pages do not say which plans include the desktop app, so confirm that on your own account. If your reason for looking at alternatives is "I don't want a bot in my meetings", Otter's own desktop app already addresses that.

## Where Otter's data goes

Otter states these facts on its privacy and security page:

- Data is stored in AWS S3 with AES-256 encryption.
- It is SOC 2 Type 2 audited and states GDPR, CCPA and HIPAA compliance.
- It de-identifies user data before using it to train its own models. It says no customer data is used to train its AI service providers' models.
- Deleted conversations stay in the trash for 30 days.

In the Otter pages I read, there is no mention of on-device transcription. Its model is hosted: your recordings and transcripts live in your Otter workspace. For many teams that is a feature, because notes are shared and searchable. For someone who wants the audio to stay on their laptop, it is the deciding difference.

<figure class="post-figure">
  <img src="{{ '/assets/blog/where-your-audio-goes.svg' | relative_url }}" alt="Diagram comparing a hosted notetaker, where recordings and transcripts are stored on the vendor's servers, with a local Mac app that records, transcribes and summarizes on the Mac and only sends transcript text out if a cloud summary is turned on" width="900" height="420" loading="lazy" style="width:100%;height:auto;display:block;border-radius:12px">
  <figcaption>Where audio goes in a hosted notetaker versus a local Mac app. Diagram by Routine Meeting, based on each vendor's own pages.</figcaption>
</figure>

## What Otter costs, and where the limits are

From Otter's pricing page, checked 2026-10-06:

| Plan | Price (per user) | Monthly minutes | Max per conversation |
|---|---|---|---|
| Basic (free) | 0 | 300 | 30 minutes; 3 lifetime file imports |
| Pro | $16.99 monthly, or $8.33 per month billed annually | 1,200 | 90 minutes; 10 imports per month |
| Business | $30 monthly, or $19.99 per month billed annually | Unlimited meetings | 4 hours |
| Enterprise | Custom | Custom | Custom (adds SSO, SCIM; HIPAA as an add-on) |

If you hit minute caps (a common complaint in Reddit threads about Otter), the reason to switch is simple: local apps have no minute meter, because the only limits are your disk and your Mac.

<figure class="post-figure">
  <img src="{{ '/assets/blog/otter-minutes-vs-local.svg' | relative_url }}" alt="Bar chart of Otter's monthly transcription minutes: 300 on Basic, 1,200 on Pro, unlimited meetings on Business, against local apps with no minute meter" width="900" height="330" loading="lazy" style="width:100%;height:auto;display:block;border-radius:12px">
  <figcaption>Otter's monthly minutes by plan, from its pricing page, versus local apps.</figcaption>
</figure>

## The alternatives, step by step

### Routine Meeting (free)

A menu-bar app that starts by itself when it hears the pattern of a real call: your microphone active plus audio coming from another app. That means it also catches Slack huddles, Discord, FaceTime and calls relayed to your Mac, with no per-app setup.

- **Capture:** microphone plus system audio through macOS ScreenCaptureKit. Audio only, no video. macOS shows its purple recording indicator.
- **Transcription:** WhisperKit on your Mac's Neural Engine, with your side and the other side transcribed separately and labeled "What you said" and "What others said".
- **Summaries:** optional. Use a fully local model (no key, no network call), or your own Gemini key, which sends the transcript text, never the audio.
- **Account and price:** none and free.
- **Requirements:** Apple Silicon, macOS 13 or later.

<figure class="post-figure">
  <img src="{{ '/screenshots/app-main.webp' | relative_url }}" alt="Routine Meeting main window: meeting list, weekly stats and the Task Radar" width="1577" height="997" loading="lazy" style="width:100%;height:auto;display:block;border-radius:12px">
  <figcaption>Routine Meeting's main window on a Mac.</figcaption>
</figure>

Limits: closed source, speaker labels are you versus everyone else (not one name per person), no team sharing, no integrations, no SOC 2 report, and no phone or web app.

### MacWhisper (Pro: 64 EUR, one time)

A mature transcriber for files and dictation that also records meetings in Zoom, Teams, Webex and more, with automatic start and end detection, no bots, and local models. Its docs describe meeting recording as a beta and say all participants are grouped as one speaker for now.

### Biscotti (free, source-available)

Fully local pipeline: Whisper V3 Turbo, per-person speaker separation and a Gemma model for summaries. Needs macOS 15 or later and recommends 16 GB of RAM.

### MacParakeet (free, GPL-3.0)

Open source, no account. Local speech recognition, separates you from everyone else, writes audio to disk every second so a crash does not lose a meeting. Summaries go to the AI provider you configure. Needs macOS 14.2 or later and Apple Silicon.

### echo99 (free)

Per its own site: records your mic and your Mac's audio locally with no bot, transcribes on-device in 25 languages (same with Wi-Fi off), recognizes recurring voices and labels them by name using local voice matching, and generates on-device summaries with key points, decisions and action items. Free, no account, no minute limits. Needs macOS 14.4 or later and runs on Apple silicon and Intel. Its live transcription is marked experimental, and it sends an anonymous install ID at launch for update checks. Treat these as the vendor's claims.

### Muesli

Per its own site: a free, open-source macOS app for Apple Silicon Macs that captures meeting audio from your computer without a bot and transcribes on-device with Parakeet or Whisper models, and adds hotkey dictation. Its page did not say whether summaries run locally or in the cloud, or whether it labels speakers, so I leave those blank.

## Side by side

| | Otter | Routine Meeting | MacWhisper | Biscotti | MacParakeet | echo99 |
|---|---|---|---|---|---|---|
| Bot-free on Mac | Yes, desktop app | Yes | Yes | Yes | Yes | Yes |
| Transcription | Hosted service | On your Mac | On your Mac | On your Mac | On your Mac | On your Mac |
| Account needed | Yes | No | No | No | No | No |
| Price | Free tier; Pro from $8.33 annual | Free | Free tier; Pro 64 EUR once | Free | Free | Free |
| Minute caps | 300 free, 1,200 Pro | None | None | None | None | None |
| Speaker labels | Speaker identification (paid plans) | You vs others | One speaker (beta docs) | Per person | You vs others | Local recognition |
| Team sharing and integrations | Yes | No | Export and automations | No | No | No |
| Compliance report | SOC 2 Type 2, HIPAA | None | None | None | None | None |
| Platforms | Web, Mac, Windows, iOS, Android, Chrome | Mac | Mac | Mac | Mac | Mac |
| Mac requirements | macOS 12.3+ (desktop app) | Apple Silicon, macOS 13+ | Not checked | macOS 15+, Apple Silicon | macOS 14.2+, Apple Silicon | macOS 14.4+, Apple silicon or Intel |

## Which should you choose?

- **You work in a team, share notes, and need integrations or a compliance report:** stay with Otter, or choose a hosted tool. A local app will not give you shared workspaces.
- **You are on a Mac and want audio kept on your machine, with no account and no minute meter:** pick a local app. Routine Meeting if you want it to start with every call, in any app. Biscotti if you want per-person speaker labels and a fully local summary. MacParakeet if you want open source.
- **You also transcribe lots of files and dictate:** MacWhisper.
- **You mostly need it for interviews or voice notes:** a file-based transcriber is cheaper than a meeting subscription; the Reddit threads on this topic point to Whisper-based tools.

## Moving from Otter to a local app

1. **Export what you need.** Download your important transcripts from Otter before cancelling; nothing local will import them.
2. **Install and grant permissions.** Microphone, and Screen and System Audio Recording. The second name sounds scary, but only audio is captured.
3. **Run it side by side for a week.** Keep Otter for team meetings while you test the local app on your own calls.
4. **Decide about summaries.** Local summaries are private but weaker than a large cloud model. Routine Meeting lets you choose per need.
5. **Check recording consent.** Local does not change the law; many places require telling participants you are recording.

## FAQ

**Is there an Otter app for Mac?** Yes. Otter has a desktop app for Mac and Windows that records without a bot, and a web app.

**Does Otter put a bot in my call?** Otter's Notetaker can join a meeting as a participant, and the desktop app lets you record without it.

**Is Otter free on Mac?** There is a free plan with 300 minutes a month and 30 minutes per conversation.

**What is a good Otter alternative that works offline?** Apps that transcribe on your device, such as Routine Meeting, Biscotti, MacParakeet and echo99, can transcribe without a connection once their models are downloaded.

**Will a local app match Otter's accuracy and summaries?** Whisper-family models are strong on clear speech. Local summaries are weaker than cloud ones, and none of the local apps offer shared workspaces or an AI chat across your whole team's meetings.

## Sources (checked 2026-10-06)

- Otter: pricing page, privacy and security page, desktop app page, help article "Otter Desktop App (Mac and Windows)", and the launch post "Introducing the Otter Desktop App" (Oct 7, 2025), all on otter.ai
- echo99: echo99.app and echo99.app/otter-alternative
- Muesli: muesli.works and muesli.works/otter-ai-alternative
- MacWhisper: macwhisper.com and docs.macwhisper.com
- MacParakeet: macparakeet.com/meetings
- Biscotti: github.com/scosman/Biscotti
