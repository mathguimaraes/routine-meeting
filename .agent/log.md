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
