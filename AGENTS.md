# Agent Operating Notes

This repo is a **public** AI founder knowledge base, distributed as a Claude Code plugin. Future Claude sessions and automation: read this first.

## Hard rules

1. **No internal/operator-specific content.** Do not reference any specific company's internal strategy, API keys, employee names, product codenames, or competitive positioning. If a transcript or article was originally added with a "what this means for company X" addendum, that addendum has been stripped — keep it that way.
2. **No `reports/` folder.** Daily-crawl status notes belong in operator-only channels (Slack, ops dashboards, private gist), not in this public repo. If you find yourself wanting to write a status report into the repo, don't — write it elsewhere or just put it in the commit message.
3. **English-only in curated layer.** `patterns/`, `by-topic/`, `by-person/`, `by-company/`, `by-source/`, `frameworks/`, `sources-catalog/` are English. `raw-transcripts/` keeps whatever language the source was in.
4. **Don't paste full transcripts into chat output.** Reference by path. Transcripts are committed once; users grep/read them directly.
5. **Don't rewrite curated entries** in `by-topic/` / `by-person/` / `by-company/` / `by-source/` / `patterns/` without good reason — those are hand-curated.

## Layout

```
patterns/             15 cross-cutting insights
by-topic/             strategy / hiring / product / fundraising / engineering-management
by-person/            ~150 founder profiles (western/ + chinese/)
by-company/           ~110 company files
by-source/            ~106 podcast/publication summaries
frameworks/           20 canonical playbooks
sources-catalog/      101 source subscriptions
sequoia-channel/      Sequoia YouTube full catalog
news-mentions/        monthly news log
raw-transcripts/      ~1,700 full transcripts (sequoia / 20vc-podcast / dwarkesh /
                      cheeky-pint / acquired / latent-space / cognitive-revolution /
                      lennys-podcast / no-priors / blog-posts)
.claude-plugin/       plugin + marketplace manifests
commands/             /kb, /kb-person, /kb-source slash commands
SKILL.md              skill definition consumed by the Claude Code plugin host
```

## How to add new content

- **A new podcast transcript** → drop into `raw-transcripts/<slug>/<filename>.txt` with the standard 4-line header (`# title`, `# URL`, `# Date`, `# source`). Update the folder's `README.md` index.
- **A new founder learning** → append to the relevant `by-person/<name>.md`, then propagate to the corresponding `by-topic/` and `by-source/` files. Use the existing `**★/★★/★★★** [Theme]:` format. Cite the source URL.
- **A new pattern** → only if it appears in 3+ independent sources. Add to `patterns/` and update `patterns/README.md`.
- **A new framework** → add to `frameworks/` with the standard header (Author, Released, URL, Signal, Topic tags).

## Commit hygiene

- Use neutral, factual commit messages. Good: `"Add 4 Latent Space transcripts (May 28-30)"`. Bad: `"Add transcripts relevant to our Q3 priorities"`.
- Don't include strategic commentary in commit bodies.
- If an automated session adds content, the commit author/email should be a generic bot identity, not a person's.

## Distribution

This repo is consumable as a Claude Code plugin:

```
/plugin marketplace add Memories-ai-labs/ai-founder-kb
/plugin install ai-founder-kb@memories-ai-labs
```

Users then query via `/kb`, `/kb-person <name>`, `/kb-source <podcast>`, or plain English. See [SKILL.md](./SKILL.md) for how Claude navigates the corpus.
