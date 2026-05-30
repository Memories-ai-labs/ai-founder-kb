---
description: Pull the index + summary for a specific podcast/publication source in the KB.
argument-hint: <source name, e.g. "Cheeky Pint", "Dwarkesh", "20VC", "Acquired", "Cognitive Revolution">
---

The user wants the KB's coverage of: **$ARGUMENTS**

Steps:

1. Look in `by-source/` for a file matching the source name (e.g., `cheeky-pint.md`, `dwarkesh-podcast.md`, `lenny-s-podcast.md`, `latent-space.md`, `cognitive-revolution.md`). Read it.
2. Check `raw-transcripts/` for a matching folder slug. If present, read its `README.md` for the episode index.
3. Reply with:
   - One-line identity of the host(s) and what the podcast covers
   - Top 3-5 curated entries from `by-source/<source>.md` (with founder name + date + theme + one-line takeaway)
   - Stats from `raw-transcripts/<slug>/`: number of episodes, size range, notable guests
   - File paths to the local transcript folder + the curated `by-source/` page
4. If we don't have it, say so and suggest the closest matches by name.
