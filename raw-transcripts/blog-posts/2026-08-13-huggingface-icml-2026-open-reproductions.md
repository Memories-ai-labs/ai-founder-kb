# What We Learned by Reproducing 2,200 Papers from ICML
# URL: https://huggingface.co/blog/icml-2026-open-reproductions
# Date: 2026-08-13
# Source: Hugging Face Blog

## Overview

Hugging Face organized a 19-day hackathon where 1,221 community members used AI agents to reproduce papers from ICML 2026. Participants published 6,816 logbooks examining 2,226 papers — approximately one-third of the conference's 6,352 accepted submissions.

## Key Findings

**Reproducibility landscape**:
- 51% of examined papers had at least one claim independently verified; 266 papers were fully reproduced
- 23% had falsifications or contested claims, including 49 papers where all claims failed verification
- 242 papers saw different teams reach opposite conclusions on identical claims

**Notable falsifications identified**:
- A paging algorithm claimed robustness of H_k + O(1) but testing revealed H_k + Θ(log k) growth
- A theoretical proof failed after step 224 with discoverable counterexamples
- One paper's theory analyzed reverse KL divergence while its code implemented forward KL

## Human-Agent Collaboration Lessons

Pure automation has limits. Most reliable results emerged when humans directed agents, questioned assumptions, and made judgment calls. Perceptual evaluations — determining whether quantized images remained usable — required human oversight.

Conclusion: humans should focus on "managing intelligence effectively" rather than replacing agents or traditional review entirely.

## Relevance for AI Founders

This study provides empirical grounding for the current state of AI-assisted scientific work:
- AI agents can handle breadth (6,816 logbooks in 19 days) but need human direction for quality
- ~25% of ML papers have reproducibility issues — significant for founders who base product bets on published research
- The human+agent collaboration model outperforms either alone — signals where AI tooling for knowledge work should be heading
