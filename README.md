# AI Founder Knowledge Base

**Compiled**: 2026-05-24
**Author**: Shawn Shen (Memories.ai exec) + Claude
**Goal**: A queryable, indexable knowledge base of founder-tier content for AI startup builders — especially those in personal memory / video AI.

## Scale

- **Learnings**: 372 entries (117 people / 108 companies / 106 interview sources)
  - Strategy 166 · Product 84 · Engineering & Mgmt 70 · Hiring 40 · Fundraising 12
  - Western 257 · Chinese-speaking 115
- **Cross-cutting patterns**: 15 recurring insights
- **Framework documents**: 19 canonical playbooks (including the Anthropic Founder Playbook)
- **Source subscriptions**: 101 podcasts/newsletters/blogs that consistently produce founder-tier content
- **Memories.ai action checklist**: 26 items prioritized P0/P1/P2
- **Sequoia YouTube channel**: 159 video metadata records (33 with transcripts)

---

## How to Use This Knowledge Base

### Install as a Claude Code plugin (recommended for teams)

```
/plugin marketplace add Memories-ai-labs/ai-founder-kb
/plugin install ai-founder-kb@memories-ai-labs
```

Then ask Claude anything — `/kb`, `/kb-person <name>`, `/kb-source <podcast>`, or just plain English. See [INSTALL.md](./INSTALL.md).

### Other access patterns

Everything is Markdown. You can also:

1. **Grep it directly**: `grep -r "hiring" .` to find anything about hiring
2. **Import to Notion**: Drop the folder into Notion — it becomes a page tree automatically
3. **Read by hand**: Start from the index below

See [HOW-TO-USE.md](./HOW-TO-USE.md) for details.

---

## Core Index (by purpose)

### 🌟 If you have limited time

Start with these two folders:

- **[Patterns (patterns/)](./patterns/)** — 15 cross-cutting insights that recur across many sources; the highest-density content
- **[Memories.ai action checklist (memories-ai-actions/)](./memories-ai-actions/)** — 26 P0/P1/P2 actions specific to Memories.ai

### 📚 Deep read by topic

- **[Strategy](./by-topic/strategy.md)** — 166 entries
- **[Product](./by-topic/product.md)** — 84 entries
- **[Engineering & Management](./by-topic/engineering-management.md)** — 70 entries
- **[Hiring](./by-topic/hiring.md)** — 40 entries
- **[Fundraising](./by-topic/fundraising.md)** — 12 entries

### 👤 By person

- **[by-person/](./by-person/)** — one file per founder; all of their learning points

### 🏢 By company

- **[by-company/](./by-company/)** — one file per company

### 🎙 By interview source

- **[by-source/](./by-source/)** — one file per podcast / publication

### 📖 Canonical framework documents

- **[frameworks/](./frameworks/)** — 20 must-read playbook documents
  - Top: [Anthropic Founder Playbook](./frameworks/anthropic-founders-playbook.md) (released 2026-05)

### 📡 Source subscription catalog

- **[sources-catalog/](./sources-catalog/)** — 100+ sources that consistently produce founder-tier content

### 🎬 Sequoia YouTube channel full catalog

- **[sequoia-channel/](./sequoia-channel/)** — 159 video metadata records + 33 transcript paths

---

## Suggested First Reads

### Top 5 cross-cutting patterns

- [#01 — The Middle Layer Gets Eaten](./patterns/01-the-middle-layer-gets-eaten.md)
- [#02 — Anti-Scaling: Fewer People + AI Agents](./patterns/02-anti-scaling-fewer-people-+-ai-agents.md)
- [#03 — Hidden Internal Capabilities = Failure Mode](./patterns/03-hidden-internal-capabilities-=-failure-mode.md)
- [#04 — Anthropic's 9 Consumer Verticals Are Left for Founders / 4 Enterprise Verticals Anthropic Keeps](./patterns/04-anthropic-s-9-consumer-verticals-are-left-for-founders-4-enterprise-verticals-an.md)
- [#05 — Asymmetric Competition / Stay Out of Big Tech's Range](./patterns/05-asymmetric-competition-stay-out-of-big-tech-s-range.md)

### Top 5 founder profiles

- [Dario Amodei (Anthropic) — Dwarkesh 2026-02 deep interview](./by-person/western/dario-amodei.md)
- [Ji Yichao (Manus) — BAAI + Zhang Xiaojun EP128](./by-person/chinese/ji-yichao.md)
- [Ivan Zhao (Notion) — Sequoia "Refounder" 63 min](./by-person/western/ivan-zhao.md)
- [Jack Dorsey (Block) — Sequoia 3-role org / 40% layoff](./by-person/western/jack-dorsey.md)
- [Wang Tao (DJI) — Huxiu, first interview in 10 years](./by-person/chinese/wang-tao.md)

### Top 3 framework documents

- [Anthropic Founder Playbook](./frameworks/anthropic-founders-playbook.md) — released 2026-05, most recent
- [Building Effective Agents](./frameworks/building-effective-agents.md) — Anthropic 2024-12
- [Bessemer State of AI 2025](./frameworks/bessemer-state-of-ai-2025.md) — benchmark report

---



### 🎙 20VC Podcast — Full Archive (added 2026-05-24)

- **[raw-transcripts/20vc-podcast/](./raw-transcripts/20vc-podcast/)** — 869 episodes of 20VC with full transcripts + structured summaries
  - 881 raw transcripts (`transcripts/*.txt`)
  - 879 per-episode summary JSONs (`summaries/*.json`)
  - `guests.json` + `index.json` with guest / company / topics / key_insights metadata
  - Categories: SaaS (172), Enterprise (130), AI/ML (117), Consumer (96), Fintech (68), and more

## Related Files (Outside This Folder)

- `/Users/junxiaoshen/Desktop/memories-ai-api-gaps-2026-05-24.md` — Memories.ai public API gap report (12 empirically tested gaps; standalone Markdown, for the engineering team)
- `/Users/junxiaoshen/Desktop/sequoia_transcripts/text/` — 33 raw Sequoia video transcripts (.txt)
- `/Users/junxiaoshen/Desktop/AI创始人访谈学习_2026-05-24.xlsx` — earlier Excel version (kept as backup; this Markdown KB is the current source of truth)

---

*Generated 2026-05-24.*