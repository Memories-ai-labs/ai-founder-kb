# Perplexity and Intelligence
# URL: https://openai.com/index/perplexity-and-intelligence/
# Date: 2026-11-22
# Source: OpenAI Blog
# Author: Jakub Pachocki, Chief Scientist at OpenAI

## Summary

OpenAI Chief Scientist Jakub Pachocki argues that tracking pretraining perplexity (cross-entropy loss) is a useful, transparent way to understand and compare AI progress across the industry. OpenAI is publishing its internal perplexity measurements publicly to enable shared safety standards, despite competitive costs of disclosure.

## Key Points

**Perplexity as capability proxy:** Modern AI training is fundamentally a compression problem — training a model to predict data well. As perplexity falls, new capabilities emerge:
- GPT-2: coherent paragraphs
- GPT-3: in-context learning from examples
- GPT-3.5: fluent conversation
- GPT-4: chain-of-thought reasoning
- Below log-perplexity ~0.8: transformative capabilities in cybersecurity, mathematics

**AI accelerating AI:** AI contributions to pretraining research could cause a sudden burst of advances, possibly as early as 2027. Alignment and monitoring may not keep pace with this acceleration.

**Proposed industry safeguards:**
- Frontier developers should agree on shared evaluation norms and transparency standards
- "Common limits" based on perplexity and other metrics: development would pause at each limit until specific monitoring milestones are met
- OpenAI is calling for multi-lab cooperation on this framework

**Limitations of perplexity as a metric:**
- Hard to compare across labs (different tokenizers, datasets)
- Doesn't map directly to specific tasks
- Ignores gains from chain-of-thought reasoning and RLHF
- Unknown theoretical floor

## Significance for AI Founders

This is a significant transparency move from OpenAI — publishing internal perplexity benchmarks is unusual in the competitive AI landscape. The proposal for industry-wide "perplexity-based pause points" is notable as an attempt at pre-competitive safety coordination. If adopted, it would create a new kind of AI governance lever — quantitative progress thresholds triggering safety reviews.
