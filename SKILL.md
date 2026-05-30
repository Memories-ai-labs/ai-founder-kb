---
name: ai-founder-kb
description: Query the AI founder knowledge base. Use whenever the user asks about AI startup strategy / hiring / product / fundraising / engineering management, what a specific founder or company has said, or wants source material from podcasts like Sequoia, 20VC, Dwarkesh, Acquired, Latent Space, Cheeky Pint, Cognitive Revolution, or Lenny's. The KB has ~400 curated learnings (English, signal-rated ★/★★/★★★) plus 1,600+ full episode transcripts. Cite specific files when you answer.
---

# AI Founder Knowledge Base

A two-layer corpus of founder-tier content for AI startup builders.

## Layout

```
patterns/             15 cross-cutting insights (highest signal — start here)
by-topic/             strategy / hiring / product / fundraising / engineering-management
by-person/            ~150 founder profiles (western/ + chinese/)
by-company/           ~110 company files
by-source/            ~106 podcast/publication summaries
frameworks/           20 canonical playbooks (Anthropic Founder Playbook + others)
sources-catalog/      101 subscriptions

raw-transcripts/      THE BIG STORAGE — full transcripts
  sequoia/            66 Sequoia YouTube transcripts
  20vc-podcast/       881 20VC episodes + summaries + guests.json
  dwarkesh/           153 Dwarkesh Patel posts
  cheeky-pint/        32 John Collison interviews
  acquired/           189 Ben+David deep-dives
  latent-space/       240 swyx + Alessio episodes
  cognitive-revolution/  275 Nathan Labenz interviews
  lennys-podcast/     52 Lenny Rachitsky items
```

## How to navigate (decision tree)

When the user asks a question, decide which folder to read in this order:

1. **"What does <founder> say about X?"** → `by-person/<name>.md` first. If empty, grep `raw-transcripts/` for the name.
2. **"What does <company> do for X?"** → `by-company/<company>.md` first.
3. **"How do top founders handle <topic>?"** → `by-topic/<topic>.md` (Strategy / Hiring / Product / Fundraising / Engineering & Management).
4. **"What's the consensus on X?"** → `patterns/` — 15 synthesized cross-cutting insights.
5. **"What's the playbook for X?"** → `frameworks/` — canonical multi-step playbooks.
6. **"What did <podcast> say about X?"** → `by-source/<podcast>.md` for curated highlights, then `raw-transcripts/<podcast>/` for the full episode.
7. **Verbatim quote needed** → `raw-transcripts/<podcast>/<slug>.txt` — always cite the file.

## Reading order for orientation

If the user asks "what's in here" or "where do I start":

1. Read `README.md` (top-level index)
2. Read `patterns/README.md` (the 15 patterns)
3. Read `frameworks/README.md` (the 20 playbooks)

## Conventions

- **Signal strength**: ★★★ verbatim/specific · ★★ substantive recap · ★ secondhand pointer
- **Regions**: `Western` vs `Chinese-speaking`
- **Themes** (file-name keys): `strategy` `hiring` `product` `fundraising` `engineering-management`
- **Quote convention**: direct founder quotes in `"double quotes"`

## Citation

When answering, cite file paths (e.g., `by-person/western/dario-amodei.md`) and any podcast source URL from the transcript header so the user can verify. Don't fabricate quotes — if you can't find a citation, say so.

## Slash commands shipped with this plugin

- `/kb` — Ask a question against the KB
- `/kb-person <name>` — Pull everything about a specific founder
- `/kb-source <podcast>` — Index of a specific podcast source

## Don't

- Don't paste full transcripts into chat output — reference by path.
- Don't write to `by-topic/`, `by-person/`, `by-company/`, `by-source/`, or `patterns/` unless explicitly asked — those are hand-curated.
- Don't translate KB content to non-English — the curated layer is English-only by convention. Raw transcripts stay in whatever language they were captured.
