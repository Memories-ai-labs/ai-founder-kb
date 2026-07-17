---
Title: Model Routing Is Simple. Until It Isn't.
Publisher: IBM Research / Hugging Face
URL: https://huggingface.co/blog/ibm-research/model-routing-is-simple-until-it-isnt
Date: 2026-07-15
Source: Hugging Face Blog
---

# Model Routing Is Simple. Until It Isn't.

*Published July 15, 2026 — Authors: Yara Rizk, Eyal Shnarch, Jason Tsay, Merve Unuvar (IBM Research)*

## Summary

IBM Research demonstrates that model routing in agentic systems — selecting which AI model to call for each task — is fundamentally a system optimization problem, not a simple classification task. The paper challenges naive assumptions about cost and complexity.

## Key Finding 1: Cost Is Counterintuitive

Tested two models on 417 AppWorld tasks. Despite GPT-4.1 having lower per-token pricing, Claude Sonnet was **49% cheaper overall** ($79 vs $155). Why: "Agent workloads tend to reuse large chunks of context across steps." Sonnet's superior cache-read pricing created cost advantages that overcome higher base rates and longer execution paths.

**Implication**: For agentic workloads, prompt caching economics dominate raw token pricing.

## Key Finding 2: Difficulty Assessment Is Hard

Simple-seeming tasks (contract summarization) can trigger hidden complexity: retrieval, compliance checks, tool use. Technically complex prompts may execute efficiently on smaller specialized models. Production routing must simultaneously balance:

- Cost
- Latency
- Model specialization
- Reliability
- Compliance / data residency / privacy constraints
- Approved model lists (enterprise governance)

## Key Finding 3: Latency Is Infrastructure-Dependent

Actual user latency depends on hardware selection, cache warmth, endpoint congestion — not just model size. Step-level routing adds overhead; task-level routing minimizes impact.

## Solution Approach

Rather than classification, treat routing as **multi-objective optimization** across cost, quality, and latency simultaneously.

**Results**: 84% accuracy for $93 with 83-second latency — 21% cost reduction and 9% latency improvement vs. running the largest model alone, accepting only 4% accuracy loss.

## Why It Matters for AI Founders

This paper has direct implications for anyone building multi-model agent systems. The cache-read pricing finding is actionable immediately: if your agent architecture uses Claude and you're paying for long-context repetition, cache pricing may already be your largest cost lever, not model selection. The framing of routing as system optimization (not classification) is the mental model shift needed before scaling agentic infrastructure.
