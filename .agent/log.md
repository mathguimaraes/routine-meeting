# Routine Meeting marketing log

(Kept outside docs/ so it is not published.)

## Open task list
1. Check Search Console indexing for all 33 sitemap URLs (needs owner; I cannot access GSC). Ask owner for the Pages/indexing report.
2. Draft replies (not post) for public threads asking for Granola/Otter/MacWhisper alternatives; find threads first.
3. Referring domains: prepare submissions for directories / alternativeto.net listing (owner must submit; AlternativeTo shows Granola alternatives pages that list competitors).
4. Add comparison pages not yet covered (Fireflies/Fathom/tl;dv bot-free alternative, Krisp, Apple Notes/Voice Memos transcription).
5. Hosting limit: site is a GitHub project page, so robots.txt at domain root is not controllable; consider custom domain (owner decision).
6. Product fact conflict: run prompt says macOS 13+, repo/site/README say 14.2+ (commit 496b5a7, 2026-11-16). Site left at 14.2+.

## 2026-11-25 (first run, no earlier log)
Observed (facts):
- Repo: 5 stars, 0 forks, 0 open issues (GitHub API, 2026-11-25). Latest release v1.13.0 published 2026-11-16 (GitHub releases).
- Sitemap lists 33 URLs; lastmod values were stale (homepage 2026-09-19 though edited 2026-11-16).
- Live-site fetch from this sandbox failed (curl returned 000, proxy), so site health unverified this run.
- WebSearch "site:mathguimaraes.github.io/routine-meeting" returned unrelated results; this tool is not Google, so indexing is unknown.
- Query "Routine Meeting Mac meeting recorder no bot on-device" (WebSearch, 2026-11-25): Routine Meeting not in results; results were Wispr Flow, Narada, Trace, Summit, HyNote, etc. Granola-alternative query: not present either; TechCrunch (2026-03-24) covered Talat.
- BlogPosting schema was absent from post layout.
Did: refreshed sitemap lastmod from git history; added BlogPosting JSON-LD to docs/_layouts/post.html (all posts).
Why: freshness signal and article entity data for AI/search crawlers. Inference: modest effect, low risk.
Not done: robots.txt (project page path would be ignored by crawlers).
Next: task 1 and 2; look for live "alternative" threads to draft replies.

## 2026-11-26
Observed (facts):
- Repo: 5 stars, 0 forks, 0 open issues, no issues ever filed (GitHub API, 2026-11-26). Latest release still v1.13.0 (2026-11-16). No new commits since 2026-11-25.
- Live site fetch from sandbox: curl returned 000 again (2026-11-26); site health UNVERIFIED. No Google access; indexing unknown.
- Attempted to read Fireflies, tl;dv and Fathom pricing pages for task 4 via web-fetch agent: all three failed (permission timeout). No vendor facts obtained. Search-result snippets from third-party "alternatives" sites are not primary sources, so I did not use them.
Did: skipped task 4 (writing it without primary sources would risk false claims). Instead prepared task 3: .agent/submissions.md (copy for AlternativeTo, Product Hunt, Show HN, MacUpdate; nothing submitted).
Inference: comparison page can be written once pricing pages are readable or owner pastes their text.
Next: retry vendor pages next run (or draft the Fireflies/Fathom/tl;dv page from owner-provided text); find live "Granola/Otter alternative" threads for task 2.
Decisions needed from owner (open): GSC indexing report (task 1); submit the kit (task 3); custom domain (task 5).

## 2026-11-27
Observed (facts):
- Repo: 5 stars, 0 forks, 0 open issues; latest release v1.13.0 (2026-11-16); last push 2026-11-26 (GitHub API, 2026-11-27).
- Live site fetch from sandbox: curl 000 again (3rd run); site health UNVERIFIED. No Google access; indexing unknown.
- WebSearch (not Google) "Routine Meeting Mac meeting recorder mathguimaraes" and Granola-alternative query: Routine Meeting absent from results (2026-11-27). Results included AlternativeTo Granola alternatives pages, Wispr Flow, Fireflies and Circleback comparison pages. WebSearch returns titles/URLs only, no thread content, so no Reddit threads found for task 2.
- Apple's Voice Memos support page was readable via the web-fetch agent (2026-11-27); Fireflies/Fathom/tl;dv pages were not retried.
Did: new post docs/_posts/2026-11-27-voice-memos-transcription-vs-meeting-recorder-mac.md (task 4, Apple Notes/Voice Memos part), using only facts read from Apple's page; unknowns (on-device vs cloud, languages, system audio) are stated as "not said". Added to sitemap.
Why: covers a "does Mac already transcribe?" query class with a primary source. Inference: small, low-risk; effect on citation unknown.
Next: retry Fireflies/Fathom/tl;dv pages via web-fetch; Krisp page; find live threads (needs a search tool that returns Reddit content).
Decisions needed from owner (open, unchanged): GSC indexing report (task 1); submit the kit in .agent/submissions.md (task 3); custom domain (task 5).
