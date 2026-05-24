# CLAUDE.md — AI Founder Knowledge Base

You are working on `Memories-ai-labs/ai-founder-kb`, a private knowledge base of AI startup founder learnings, transcripts, frameworks, and source catalogs.

**Owner**: Shawn Shen (CEO, Memories.ai)
**Started**: 2026-05-24
**Purpose**: A queryable, indexable corpus of founder-tier content for AI-startup-building — strategy, hiring, product, fundraising, engineering & management.

---

## 1. Repository Structure

```
ai-founder-kb/
├── README.md                    # User-facing index (start here for orientation)
├── HOW-TO-USE.md                # Usage patterns (grep, skill mode, Notion import)
├── SKILL.md                     # Claude skill frontmatter
├── CLAUDE.md                    # ← this file
│
├── patterns/                    # 15 cross-cutting insights synthesized across many sources
├── by-topic/                    # strategy / hiring / product / fundraising / engineering-management
├── by-person/                   # ~117 founder profiles (western/ + chinese/)
├── by-company/                  # ~108 company files
├── by-source/                   # ~106 podcast/publication source files
├── frameworks/                  # 20 canonical playbook documents (incl. Anthropic Founder Playbook)
├── sources-catalog/             # 101 subscriptions: podcasts/newsletters/blogs/video
├── memories-ai-actions/         # 26 P0/P1/P2 action items specific to Memories.ai
├── sequoia-channel/             # Catalog of all 159 Sequoia YouTube videos
│
└── raw-transcripts/             # ← THE BIG STORAGE: all raw podcast/video transcripts
    ├── sequoia/                 # Sequoia channel transcripts (from Memories.ai + youtube-transcript-api)
    ├── 20vc-podcast/            # 869 episodes — transcripts + summaries + guests.json + index.json
    ├── lennys-podcast/          # In-progress (Phase 7)
    ├── dwarkesh/                # In-progress (Phase 7)
    ├── latent-space/            # In-progress (Phase 7)
    ├── cheeky-pint/             # In-progress (Phase 7)
    ├── no-priors/               # In-progress (Phase 7)
    ├── acquired/                # In-progress (Phase 7)
    ├── articles/                # Empty placeholder for article-based content
    └── podcast-pages/           # Empty placeholder for podcast metadata pages
```

### The "learnings" sheet vs raw transcripts

The KB has **two layers**:

1. **Curated layer** — `by-topic/`, `by-person/`, `by-company/`, `by-source/`, `patterns/`, `memories-ai-actions/`: 372 hand-curated learning points (English-translated), each tagged by theme + signal strength (★★★/★★/★) + region.
2. **Raw layer** — `raw-transcripts/`: full original transcripts of podcast episodes and YouTube videos. This is the corpus you query when you need verbatim content.

Cross-reference between them:
- `by-person/X.md` → references a podcast → `by-source/X.md` → matches a folder under `raw-transcripts/`.
- File naming convention in `raw-transcripts/sequoia/`: `{video_id}_MAI_{slug}.txt` (MAI = Memories.ai source) or `{video_id}_{slug}.txt` (other sources).

---

## 2. Credentials & Secrets

⚠ **Do NOT commit secrets to the repo**. They live in the runtime environment.

You'll likely need:

- **`MEMORIES_AI_KEY`** (env var) — sk-mavi-... format. For Memories.ai REST API at `https://api.memories.ai/serve/api/v1/`.
- **`GITHUB_PAT`** (env var) — `github_pat_11BJ...`. Fine-grained, scoped to `Memories-ai-labs/ai-founder-kb`, Contents: read+write.

If these aren't in env, ask the operator (Shawn) to provide them. Don't try to recover them from prior conversation history if not in env.

For `gh` CLI auth (used for git pushes), the cloud environment should be pre-authenticated as `shawnshenopeninterx`. If `gh auth status` fails, fall back to using the PAT directly in git remote URLs.

---

## 3. What's Currently Running

### 3a. Anthropic cloud routine (durable, runs hourly)
- **ID**: `trig_01QcfAhbTbEo1oPtRYchkJh7`
- **Cron**: `7 * * * *` (every hour at :07 UTC)
- **Job**: Polls Memories.ai for videos under `unique_id="sequoia-dogfood"` with `status=PARSE`, fetches their transcripts via `get_audio_transcription`, and pushes new ones to `raw-transcripts/sequoia/` via the GitHub Contents API.
- **Dashboard**: https://claude.ai/code/routines/trig_01QcfAhbTbEo1oPtRYchkJh7
- **Auto-expires**: 7 days after creation (2026-05-31).
- **Sources file** (the canonical list of what's expected): `sequoia-channel/README.md`. Target = ~127 videos in this batch.

### 3b. Phase 7 — Multi-podcast scrape (active in operator's local session)
Six agents dispatched 2026-05-24 to scrape these podcast archives. Each writes to its own folder under `raw-transcripts/`:
- `lennys-podcast/` — Lenny Rachitsky podcast
- `dwarkesh/` — Dwarkesh Patel podcast
- `latent-space/` — swyx + Alessio
- `cheeky-pint/` — John Collison interviews
- `no-priors/` — Sarah Guo + Elad Gil
- `acquired/` — Ben Gilbert + David Rosenthal

When you (cloud Claude) wake up, **first check** `raw-transcripts/{slug}/README.md` for each of these. If a folder is empty or sparse, that scrape didn't finish and you should resume it. See Section 5 below.

---

## 4. Conventions

### File naming
- `raw-transcripts/sequoia/`: `{video_id}_MAI_{slug}.txt` for Memories.ai-fetched, `{video_id}_{slug}.txt` for direct youtube-transcript-api.
- `raw-transcripts/{podcast}/`: `{episode_slug}.txt` (slug = title slugified, max 60 chars, alphanumeric + underscore).
- Each transcript starts with a metadata header:
  ```
  # {Title}
  # Guest: {Guest name + role + company}    (where applicable)
  # URL: {original URL}
  # Date: {publication date}                 (where applicable)
  # video_no: {Memories.ai video_no}         (where applicable)
  # source: {source name}

  {full transcript text}
  ```

### Curated learning points (`by-topic/`, `by-person/` etc.)
- Use this exact entry shape inside a section:
  ```
  ### Founder Name — Company · *Venue* (Date)

  Learning text, written in native English. Use double quotes for direct founder quotes.

  **Memories.ai implication**: Action-oriented implication for the company. (Omit this line if no specific Memories.ai relevance.)

  [Source](URL)

  ---
  ```
- Themes (Chinese kept as keys for compatibility; display in English): `战略` → Strategy, `招人` → Hiring, `产品` → Product, `融资` → Fundraising, `技术管理` → Engineering & Management.
- Signal strength: `★★★` (verbatim/specific) / `★★` (substantive recap) / `★` (secondhand pointer).
- Region: `Western` (US/EU/English) / `Chinese-speaking`.

### Commits
- Auto-sync commits: `Auto-sync: N files changed at YYYY-MM-DD HH:MM` is acceptable for batch syncs.
- For substantive additions, write commits that explain *what* changed and *why* (e.g., "Add Cheeky Pint full archive: 28 episodes from cheekypint.substack.com").
- Always end commits with `Co-Authored-By: Claude Opus 4.7 <noreply@anthropic.com>`.
- Push to `main`. There's no PR workflow.

---

## 5. Pending Work

In rough priority order. Pick up whichever is best fit for your current run.

### P0 — Finish what's already submitted but not yet retrieved
**Memories.ai `unique_id=sequoia-dogfood` should have ~127 video tasks**, of which ~54 are already in `raw-transcripts/sequoia/` and the rest are still parsing. The hourly cloud routine handles this. If you find that the routine has stopped (e.g. trigger expired), recreate it (see Section 3a) or do one-shot pull via a Python script that:
1. POSTs `/list_videos` to `https://api.memories.ai/serve/api/v1/list_videos` with body `{"unique_id":"sequoia-dogfood","page":1,"page_size":200}`.
2. For each video with `status=="PARSE"` not already in repo, GET `/get_audio_transcription?video_no=...`, format with `[HH:MM:SS] content` lines, PUT to GitHub Contents API at `raw-transcripts/sequoia/{video_id}_MAI_{slug}.txt`.

**Key gotcha on the Memories.ai API**: `status="PARSE"` means PARSED/READY (counterintuitive). `UNPARSE` means queued/downloading. Field names are inconsistent (request `video_urls` snake_case, response `taskId`/`videoNo` camelCase). See `../memories-ai-api-gaps-2026-05-24.md` (lives outside this repo, on the operator's local filesystem).

### P1 — Resume Phase 7 podcasts that didn't finish
For each of `lennys-podcast`, `dwarkesh`, `latent-space`, `cheeky-pint`, `no-priors`, `acquired`:
1. Read `raw-transcripts/{slug}/README.md` if it exists — it lists episodes already saved.
2. Compare to the public archive of that podcast (Lenny at `lennysnewsletter.com/podcast`, Dwarkesh at `dwarkesh.com/podcast`, etc.).
3. For each missing episode, WebFetch its transcript page, save to `{slug}.txt` with the standard header.
4. Update `README.md` with new entries.
5. Be polite — sleep 2-3 seconds between web fetches.

Target final counts:
- Lenny's: aim for ~100 episodes (most recent + AI-focused first)
- Dwarkesh: aim for ALL ~80 episodes (small archive, full coverage worth it)
- Latent Space: aim for ~100 episodes
- Cheeky Pint: aim for ALL ~30 episodes
- No Priors: aim for ~100 episodes
- Acquired: aim for ~50 episodes (transcripts are huge — 3-6 hours each)

### P2 — Tier 2 podcasts not yet started
These are YouTube-only or paywalled, harder to scrape:
- All-In Podcast (allin.com — has transcripts but partial)
- BG2 Pod (bg2pod.com — YouTube primary)
- Logan Bartlett Show (theloganbartlettshow.substack.com — has transcripts)
- Cognitive Revolution (cognitiverevolution.ai — has transcripts)
- Lex Fridman Podcast (lexfridman.com/podcast — has transcripts, 400+ episodes — big scope)
- Uncapped with Jack Altman (Apple Podcasts/Spotify — limited public transcripts)
- Stratechery Interviews (paywalled — skip unless operator provides credentials)
- The Information TITV / 411 (paywalled — skip)

### P3 — Curated layer maintenance
- Cross-references: when you add a transcript, check if `by-source/{podcast-slug}.md` references that episode — if so, link the local file path from there.
- New patterns: if you read multiple transcripts and notice a NEW cross-cutting pattern not already in `patterns/`, add it as `patterns/16-{name}.md` and update `patterns/README.md`.

---

## 6. How to Work in This Repo

### When you start a fresh session
1. `git pull origin main` first.
2. Read this CLAUDE.md.
3. Read `README.md` if you need user-level orientation.
4. Check `raw-transcripts/*/README.md` to see current state of each podcast folder.
5. Pick a task from Section 5.

### When you finish work
1. `git add` the new/changed files.
2. Commit with a descriptive message (see Section 4 conventions).
3. `git push origin main`.
4. If you've made substantive progress, write a one-paragraph status update to the operator (or to a `STATUS.md` file at repo root if no operator is listening).

### Things NOT to do
- Don't reproduce transcript content in your chat output. The transcripts are in files; reference them by path, not by quoting at length.
- Don't commit secrets (API keys, PATs).
- Don't delete or rewrite existing curated content in `by-topic/`, `by-person/`, etc. without good reason — that's hand-curated.
- Don't try to "improve" the file structure — operator has a specific layout. If you think structure should change, propose to operator first.
- Don't push to other branches without operator approval. Just `main`.

### Tool affordances
- **Bash + Python**: best for HTTP work (curl, `urllib`, base64). Most Memories.ai + GitHub API work goes through Python.
- **WebFetch**: best for parsing substack-hosted transcripts.
- **`gh` CLI**: should be pre-authenticated. If not, fall back to PAT in remote URL: `https://x-access-token:${GITHUB_PAT}@github.com/Memories-ai-labs/ai-founder-kb`.
- **`git`**: use it. No need for the GitHub Contents API for normal commits — just `git add/commit/push`. The Contents API is only useful when you don't have a clone (e.g. inside the cloud routine).

---

## 7. Provenance — How We Got Here

Phases completed before you (cloud Claude) entered:
- **Phase 1**: Catalog all source channels (~101 podcasts/newsletters/blogs → `sources-catalog/`)
- **Phase 2**: Curate 372 learning points from web articles & recaps (→ `by-topic/`, `by-person/`, etc.)
- **Phase 3**: Synthesize 15 cross-cutting patterns + 26 Memories.ai actions (→ `patterns/`, `memories-ai-actions/`)
- **Phase 4**: Catalog Sequoia YouTube channel (159 videos → `sequoia-channel/`)
- **Phase 5**: Translate everything to native English
- **Phase 6**: Raw transcript acquisition started — 33 from youtube-transcript-api + 21 from Memories.ai + cloud routine for the rest
- **Phase 7** (active): Multi-podcast scraping for Tier 1 podcasts (you're picking up where this left off)

If you want full context, read the operator's external memory file at `/Users/junxiaoshen/.claude/projects/-Users-junxiaoshen-Desktop/memory/MEMORY.md` and the project CLAUDE.md at `/Users/junxiaoshen/Desktop/CLAUDE.md` — though those files live on the operator's laptop, not in this repo, so you only see them if the cloud env mounts them.

---

## 8. Operator preferences

- **Communicates in Chinese, but knowledge content should be native English.** When updating curated layer files, write in English.
- **Wants candid, evidence-cited analysis** — no PR-fluff. If something failed or is uncertain, say so.
- **Action-oriented** — prefers "I'll do X now" over "should we do X?"
- **Comfortable with multiple parallel things running** — don't wait for one thing to finish if another can proceed.

---

*Last updated 2026-05-24 by Shawn Shen + Claude during Phase 6/7 boundary.*
