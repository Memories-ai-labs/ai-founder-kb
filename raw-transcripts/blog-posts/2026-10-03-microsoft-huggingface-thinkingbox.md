# The Agent Said It Was Done. The Database Disagreed.
# URL: https://huggingface.co/blog/microsoft/thinkingbox
# Date: 2026-10-03
# source: HuggingFace Blog / Microsoft

Author: Tuhin Kundu (Microsoft)

## Summary

Microsoft and Hugging Face introduce ThinkingBox, a benchmark framework that evaluates AI agents by examining actual database states and side effects produced, rather than simply analyzing tool calls or generated text.

## Core Problem

A customer service example: an AI agent made nine proper tool calls and reported a ticket as resolved, yet failed its actual objective. The carrier exception remained open, making the terminal database state the true measure of success, not the agent's final response.

Key finding: "A trajectory is a claim. Database state is the evidence. Repetition is the trust test."

## Key Metrics

ThinkingBox introduces three measurement approaches:
- **pass@1**: Single-attempt success rate
- **pass@20**: Whether a task succeeds at least once in 20 independent runs
- **observed 20/20**: Tasks passing all 20 recorded attempts

Only three models retain most of their single-attempt accuracy across repetitions: GPT-6 Astra (78%), Claude Opus 5.5 (71%), and Claude Opus 5 (71%).

## Performance Paradox

Kimi-K3, an open-weight model, solves the broadest range of tasks (93.89% pass@20) but succeeds consistently on only 13.41% of them. Claude Opus 5, by contrast, solves fewer tasks overall but maintains consistency on 47.53% of attempts.

## Cost Analysis

Under cost-per-success, GPT-5.6 Sol leads at $0.127 per task. GPT-5.4 achieves the lowest cost-per-dependable-task at $6.80 for tasks passing all 20 runs.

## Failure Patterns

Analysis of 79,853 failed trials across 12 models:
- 79.9% tool handling issues
- 10.3% wrong state updates
- 7% incomplete user resolutions
- 2.9% lack state-changing actions entirely

## Accessibility

ThinkingBox available on Hugging Face as an OpenEnv environment. Benchmark dataset and framework open-sourced under MIT and CDLA-Permissive-2.0 licenses.
