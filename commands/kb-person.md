---
description: Look up everything the KB has on a specific founder (curated learnings + raw transcript appearances).
argument-hint: <founder name, e.g. "Dario Amodei">
---

The user is asking about: **$ARGUMENTS**

Steps:

1. Look in `by-person/western/` and `by-person/chinese/` for a file matching the name (slugified — try lowercased, hyphenated). If found, read it and summarize the curated learnings.
2. Grep `by-source/`, `by-company/`, and `patterns/` for the person's name — they may be referenced from other angles.
3. Grep `raw-transcripts/` (excluding the 20vc-podcast/transcripts/ folder which uses opaque video-id filenames) for the person's name. List up to 5 transcript file paths that match.
4. Synthesize a profile (≤300 words):
   - One-line identity (current role / company)
   - Top 3-5 ★★/★★★ insights with theme tag, brief context, source citation
   - List of transcript file paths for deeper reading

If no curated profile exists but the person appears in transcripts, surface that fact instead of making it up.
