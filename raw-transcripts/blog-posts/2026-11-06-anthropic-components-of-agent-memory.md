# The components of agent memory
# URL: https://www.anthropic.com/research/components-of-agent-memory
# Date: 2026-11-06
# Source: Anthropic Engineering

Author: Lance Martin (Anthropic Engineering)

## Key Points

- **Dreaming analogy:** Agents can review logs and transcripts between sessions to fix mistakes, write notes, and build new memory representations — analogous to the brain's offline consolidation during sleep.

- **Memory notes:** Claude can save salient observations as it works. Writing a note is a prediction that information will be useful later. On CL-Bench database tasks, newer Claude models got better at building learning loops from their notes.

- **Salience judgment:** In Pokémon Red, Claude Fable 5 wrote a small, targeted memory folder and progressed further than Sonnet 3.7, which wrote 413 files (many quickly outdated).

- **Steering vs. rules:** Telling Claude what memory is *for* works better than prescribing rules. Rules like "record only failures" reduced performance gains for stronger models.

- **Correcting memory ("dreaming"):** Dreaming checked a wrong note against session transcripts. In Pokémon, this fixed a navigation error blocking progress.

- **Wikis:** On ~350,000 files, wiki-building over 128 sessions raised evaluation scores from 13% to 48%. Combining wiki with search performed best.

- **Injected context:** Dreaming can promote key notes to the top of the memory hierarchy (loads into every session). This layer must stay small — oversized instruction files reduce adherence.

- **Open questions:** When to write memory (in-the-moment vs. background), keeping memory current, compute cost of maintenance.

## Significance for AI Founders

Practical guidance on agentic memory architecture. The "wiki + search" combo outperforms pure in-context retrieval. The dreaming/offline consolidation pattern is a reproducible technique for long-horizon agents. Key insight: prescriptive memory rules hurt strong models — tell the agent the *purpose* of memory instead.
