# Introducing Claude Sonnet 5.5
# URL: https://www.anthropic.com/claude-sonnet-5-5
# Date: 2026-09-28
# Source: Anthropic

## Overview

Claude Sonnet 5.5 is a significant upgrade to Sonnet 5, offering performance improvements alongside cost and speed advantages. The model functions as a faster, more economical alternative to Claude Opus 5.5, targeting well-defined routine tasks rather than complex analytical work.

## Performance Highlights

- **Agentic Coding:** 70.6% on Terminal-Bench 4.0 (vs Sonnet 5's 10.3%)
- **Knowledge Work:** Scores nearly equivalent to Opus 5.5 on GDPval-AA assessments
- **Visual Understanding:** First Sonnet model to defeat Pokémon Red using only screenshots
- **Speed:** 30%+ faster output than predecessor

Sonnet 5.5 demonstrates "better judgment than Sonnet 5 across different levels of complexity, while spending significantly fewer output tokens" and improved efficiency in batching tool calls.

## Cost Structure

Pricing identical to Sonnet 5:
- Input: $2 per million tokens
- Output: $10 per million tokens
- Cache reads: $0.20 per million tokens

Practical cost reduction ~30% due to fewer tokens per task.

## Safety

- Cybersecurity safeguards comparable to Opus 5.5 (first Sonnet with such protections)
- Biology safeguards matching Sonnet 5 standards
- Distillation-attack prevention through safety classifiers

## Availability

Available on AWS, Google Cloud, and Microsoft Azure. Zero data retention options available.
