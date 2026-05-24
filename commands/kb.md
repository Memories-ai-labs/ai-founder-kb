---
description: Answer a question using the AI Founder Knowledge Base (~400 curated learnings + 1,600 podcast transcripts).
argument-hint: <your question, e.g. "How do top AI founders think about pricing?">
---

Answer the user's question using the AI Founder Knowledge Base shipped with this plugin (the `ai-founder-kb` skill).

User question:

$ARGUMENTS

Process:

1. Use the decision tree in the skill's `SKILL.md` to choose the most relevant folder(s) — usually `patterns/`, `by-topic/`, `by-person/`, or `by-company/`.
2. Read the relevant curated `.md` file(s) directly.
3. If the curated layer is thin on the question, grep `raw-transcripts/` for keywords; read the top 1-2 matches.
4. Synthesize a concise answer (≤200 words) that cites specific file paths and, where possible, the founder + venue + date (e.g., "Dario Amodei — Cheeky Pint (2025-08-06)").
5. End with a short bulleted list of "Sources read" so the user can dive deeper.

If the KB doesn't cover it, say so explicitly — don't fabricate.
