# Leanstral 1.5: Proof Abundance for All
**Source:** Mistral AI
**URL:** https://mistral.ai/news/leanstral-1-5
**Date:** 2026-07-02
**Category:** Open Source / Formal Verification / AI Engineering

---

## Summary

Mistral AI released Leanstral 1.5, an open-source formal verification model (Apache-2.0) built for Lean 4. The model uses a mixture-of-experts architecture: 119B total parameters, only 6B active — delivering strong benchmark performance at low inference cost.

## Key Performance Benchmarks

- **miniF2F**: 100% accuracy (saturated)
- **PutnamBench**: 587/672 problems solved (undergraduate-to-graduate math competition problems)
- **FATE-H** (graduate-level algebra): 87% accuracy
- **FATE-X** (PhD-level problems): 34% accuracy
- Strong test-time scaling across millions of tokens

Significantly outperforms larger open-source models and Claude Sonnet on cost-adjusted benchmarks (FLTEval: 26.3 score at $36 vs Sonnet's 23.7 at $549).

## Training Methodology

Three-stage training:
1. **Mid-training** — domain adaptation
2. **Supervised fine-tuning** — curated proof data
3. **Reinforcement learning via CISPO** — multiturn compiler feedback loop

Two training environments:
- **Multiturn proving**: model receives real Lean 4 compiler feedback while solving theorems
- **Code agent environment**: simulates real development workflows with file editing and bash commands

## Real-World Applications Demonstrated

- Proved time-complexity guarantees for AVL tree implementations across 2.7M tokens
- Uncovered 5 previously unreported bugs in open-source repositories, including an integer overflow vulnerability in zigzag decoding logic

## Availability

- Weights on Hugging Face (Apache-2.0)
- Free API endpoint via Mistral infrastructure ("labs-leanstral-2603")
- Integrated into Mistral Vibe chat interface
- Supports lean-lsp-mcp (Model Context Protocol integration)

## Founder Relevance

For AI startup founders building in formal verification, code reliability, or developer tools: Leanstral 1.5 sets a new open-weight baseline for Lean 4 code verification. Its real-world bug discovery (vs. pure benchmark performance) and cost efficiency make it practical for integrating verification into CI/CD pipelines without frontier-model costs.
