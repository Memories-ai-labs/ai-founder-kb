# Install `ai-founder-kb` as a Claude Code plugin

This repo is a self-contained Claude Code plugin. Teammates can install it in any Claude Code project (CLI, web, IDE) and the KB becomes queryable from within their normal Claude conversation.

## One-time install (recommended)

In Claude Code (any project):

```
/plugin marketplace add Memories-ai-labs/ai-founder-kb
/plugin install ai-founder-kb@memories-ai-labs
```

That's it. Claude now knows about the KB. Try:

```
/kb How do top AI founders think about pricing?
/kb-person Dario Amodei
/kb-source Cheeky Pint
```

Or just ask in plain English — the `ai-founder-kb` skill description triggers Claude to read the relevant files automatically:

> What does Patrick Collison say about hiring?
>
> Show me the Anthropic founder playbook.
>
> Summarize the 15 patterns.

## What gets installed

- **One skill** (`ai-founder-kb`) — the navigation guide in `SKILL.md`. Claude auto-loads it when relevant questions come up.
- **Three slash commands** — `/kb`, `/kb-person`, `/kb-source` (see `commands/`).
- **The full KB content** — `patterns/`, `by-topic/`, `by-person/`, `by-company/`, `by-source/`, `frameworks/`, `sources-catalog/`, `memories-ai-actions/`, `raw-transcripts/`. Claude lazy-loads files only when needed.

## Alternative: local clone (for development)

If you want to edit the KB locally:

```bash
git clone https://github.com/Memories-ai-labs/ai-founder-kb.git
cd ai-founder-kb
claude --plugin-dir .
```

## Update

```
/plugin update ai-founder-kb@memories-ai-labs
```

## Uninstall

```
/plugin uninstall ai-founder-kb@memories-ai-labs
/plugin marketplace remove memories-ai-labs
```

## Permissions / credentials

This plugin is content-only. No MCP servers, no API keys required, no outbound network calls. Claude reads files locally.

If you also want the auto-update pipeline (fetching new podcast transcripts), see `CLAUDE.md` §3a — that's a separate Anthropic cloud routine, not part of the plugin.
