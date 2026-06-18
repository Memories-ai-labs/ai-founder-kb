# Is It Agentic Enough? Benchmarking Open Models on Your Own Tooling
# Source: Hugging Face Blog
# URL: https://huggingface.co/blog/is-it-agentic-enough
# Date: 2026-06-18
# Publisher: Hugging Face
# Authors: Lysandre, Nathan Habib, Pedro Cuenca, and contributors

---

This post explores how to evaluate software libraries for agent-driven usage. Rather than checking if agents produce correct answers, the authors measure the effort required — token consumption, latency, and execution paths — across different model sizes and library revisions.

## Core Argument

Two different paths to identical results carry vastly different costs. One agent might write a 40-line Python script with debugging cycles, while another executes a single CLI command. Traditional evaluation misses these distinctions.

Key principle: "If it isn't tested, then it doesn't work; if it isn't documented, then it doesn't exist." Both apply to agentic tooling, where discoverability and clear documentation directly influence agent efficiency.

## Evaluation Framework

Three "tiers" of agent access tested:
- **bare**: standard library installation only
- **clone**: full source repository available locally
- **skill**: packaged documentation and examples in context

Metrics: match percentage, median time, token usage (new/cached/generated), error rates, and custom "markers" indicating behaviors like CLI adoption or API usage choices.

## Findings on Transformers

Testing a CLI and Skill addition to the `transformers` library revealed nuanced tradeoffs:

**Large models** benefited from new affordances — fewer turns with Skill variant, though higher input token usage initially while discovering the new interface.

**Small models** showed degraded performance. The smallest models struggled with ambiguity introduced by the Skill, sometimes misinterpreting documented CLI tools as callable functions. One model dropped from 100% accuracy to 0% on sentiment classification when the Skill was introduced.

## Critical Insight

Beneficial changes for capable models can paradoxically harm smaller ones by introducing interpretive ambiguity. This argues for evaluating agent-facing APIs across the full model spectrum before shipping.

## Practical Application

The `agent-eval` CLI makes the harness portable. Users define tasks, expected outputs, and relevant revisions, then fan execution across parallel jobs on Hugging Face infrastructure for fair hardware comparison. Results render in an interactive dashboard with shareable traces.
