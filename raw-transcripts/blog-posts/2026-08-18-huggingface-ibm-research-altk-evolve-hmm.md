---
Title: How Much Memory Does Your Agent Actually Need?
Author: Vatche Isahagian, Gaodan Fang, Jayaram Radhakrishnan et al. (IBM Research)
URL: https://huggingface.co/blog/ibm-research/altk-evolve-hmm
Date: 2026-08-18
Source: Hugging Face Blog
---

## Summary

IBM Research examines how to optimize agentic memory across different model capability tiers using ALTK-Evolve, a system for self-distilled learning without weight updates. Core finding: optimal memory strategy depends on model tier, not just task type.

## Three Patterns by Model Tier

1. **Strong models with capacity**: Benefit from full guideline sets. DeepSeek-V3.2 improved +9.5pp task completion with complete guidelines.
2. **Weaker/mid-tier models**: Perform better with selective retrieval — compact core + task-relevant guidelines. gpt-oss-120b achieved +16.1pp gains at only 5% token overhead.
3. **Saturated models**: No measurable improvement from memory augmentation (performance ceiling).

## Core Insight

"Agentic memory is not a feature you switch on. It's a dose you calibrate to the model."

## Technical Approach

The system extracts behavioral guidelines from successful and unsuccessful task trajectories, consolidates them, then either injects the full set or retrieves task-relevant selections at inference time — no weight updates required.

## Practical Implications for AI Builders

- Don't inject all available context uniformly; calibrate memory to model capability
- Prompt caching makes full guideline sets affordable for strong models in production
- Curated retrieval (selective injection) is the right strategy for mid-tier models deployed at cost
- Framework is model-agnostic and can be applied without retraining
