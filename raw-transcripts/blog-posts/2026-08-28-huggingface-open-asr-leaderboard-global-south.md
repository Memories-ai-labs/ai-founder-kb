# The Open ASR Leaderboard Adds Its First Global South Language
# URL: https://huggingface.co/blog/open-asr-leaderboard-global-south
# Date: 2026-08-28
# Source: Hugging Face Blog

Authors: Eric Bezzam, Shobhit Banga, and Voice Arena team

## Overview

Hugging Face and Voice Arena introduced Hindi and Indian English evaluation sets to the Open ASR Leaderboard — the first Global South language on this multilingual benchmark platform.

## Key Contributions

**Dataset Composition:**
- 4,888 speakers across Hindi and Indian English variants (four speaker-disjoint splits)
- Indian English public set: 1,444 speakers, 5.62 hours of audio
- Hindi: 468 public speakers, 1,571 private speakers (~1.33 and 4.47 hours)

**Design Philosophy:**
Varies across 9 dimensions: geography, age, gender, vocabulary, devices, acoustic environments, speech type, speech rate, and multiple valid transcripts. Speaker diversity prioritized — >50% of speakers contribute exactly one segment.

## Technical Innovation

**Orthographically-Informed Word Error Rate (OIWER):** Accepts multiple valid spelling variants via lattice-based scoring — addresses Hindi's code-mixing and orthographic variation challenges.

**Metadata Richness:** 18 fields per segment covering demographics, geography, recording conditions, and speaker background.

## Impact

Models ranking identically on aggregate metrics showed dramatically different regional performance — up to 1.68 points variance across geographic zones. Aggregate scores mask regional capability gaps.

## Access

Self-scoring available via pull requests to Open ASR Leaderboard GitHub; private splits evaluated by Hugging Face team.
