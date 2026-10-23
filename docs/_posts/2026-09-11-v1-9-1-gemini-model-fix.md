---
layout: post
title: "v1.9.1: AI summaries fixed after Google retired a Gemini model"
description: "Summaries, insights and daily reports were failing with a 404 because Google retired the model the backend fell back to. Fixed, with a sturdier fallback chain."
categories: [updates]
date: 2026-09-11
version: "1.9.1"
---

If AI Summaries, Insights or Daily Reports were failing with "Insights failed" and a 404 error, this is the fix.

Google retired the `gemini-2.0-flash` model, and the summary backend fell back to it when the first-choice model was under load. When that fallback disappeared, the whole request failed instead of just moving on. 1.9.1 replaces the retired model, and the fallback chain now treats a retired-model response as recoverable: it tries the next model rather than giving up.

Nothing else changed in this release. Recordings and on-device transcription were never affected, only the cloud summary step.

[Download v1.9.1](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.9.1) · [Full release notes](https://github.com/mathguimaraes/routine-meeting/releases/tag/v1.9.1)
