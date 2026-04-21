# Dealroom Post Engine

A Claude-powered LinkedIn ghostwriting pipeline built in under 5 hours as a job application to Shamus Madan at Dealroom Media.

## What it does

Three modules, one screen:

1. **Voice Profile** — ingests a founder's public writing (LinkedIn, podcast, newsletter, Medium) and extracts a structured voice spec: tone axes, hook patterns, signature phrases, formatting tics, taboo words, non-negotiables.
2. **Hook Lab** — generates hook variants per idea and grades each one on three axes (emotion, value, credibility). Outputs `ship`, `rewrite`, or `kill` verdicts with rewrite suggestions.
3. **Drafts** — writes full posts in the target voice using top-graded hooks, with ICP flagging (pipeline vs vanity).

## Why it exists

Dealroom Media writes LinkedIn posts for founders backed by a16z, Sequoia, Benioff, and Kevin Durant — with a 5-writer team. Voice fidelity is the bottleneck as writers scale across clients. This tool compresses the onboarding-a-new-writer-to-a-new-client workflow from days to minutes.

## Stack

- Voice extraction, hook generation, hook grading, drafting: Claude (Opus 4.7 for judgment-heavy steps, Sonnet 4.6 for generation)
- UI: single-file HTML, Tailwind via CDN, embedded JSON, vanilla JS. No build step, no backend, no API keys required to view the demo.
- Deploy: drag-and-drop to Vercel or any static host.

The live version (with a running API backend) is ~30 lines of Python behind a Claude API call. Ships in a day behind a login.

## Files

```
voice_profile.json          — extracted voice spec, subject: Shamus Madan
voice_in_plain_english.md   — one-paragraph prose summary
posts_corpus.md             — raw LinkedIn posts used for extraction
hooks.json                  — 25 generated hooks with E/V/C scores
drafts.json                 — 5 full post drafts
index.html                  — the demo UI (open in any browser)
loom_script.md              — the 3-minute Loom recording script
dm_template.md              — LinkedIn DM to send with the Loom
README.md                   — this file
```

## Run it

Open `index.html` in Chrome. Everything is embedded.

## Extend it (live version)

- Paste a target founder's LinkedIn posts into a text field → voice profile re-generates via Claude API
- Enter a raw idea → hooks generate → grader scores → top hook drafts a full post
- Export approved posts to Notion or client's preferred tool

## Author

Saif — I build cool shit, do hard stuff, stay curious.
