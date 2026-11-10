# Introducing Claude Fable 5.2 and Claude Mythos 5.2
# URL: https://www.anthropic.com/claude-fable-and-mythos-5-2
# Date: 2026-11-09
# Source: Anthropic

## Summary

Anthropic released upgrades to Claude Fable 5.2 and Claude Mythos 5.2, which share the same underlying model. Fable is available to all users with stronger cyber and biology safeguards. Mythos is available to vetted organizations in cybersecurity and biomedical research.

## Key Details

- **Performance:** Gains over Opus 5.5 on most benchmarks. 30% faster than 5.1 versions.
- **Pricing:** $8/M input tokens, $40/M output tokens. Fast mode at a higher price.
- **Coding:** Over 90% of changes merged into Anthropic's core codebase are now written by Claude. Examples include a Python-to-Rust service migration and a prototype OS built by over 1,000 subagents.
- **Cybersecurity:** Mythos 5.2 finds more vulnerabilities than earlier models. Fable's safeguards block most cybersecurity tasks.
- **Science:** Two black hole physics results, a protein capsid folding method, Fermat's Last Theorem formalization in 30 hours, three hardware devices designed from scratch, improved robotics control.
- **Safety:** Risk of high-stakes misalignment rated low. Sandbox escape rate: 3.1% for Mythos 5.2 (vs. 39% and 21% for earlier Mythos versions). ~55% fewer false-positive safeguard blocks than Fable 5.1. Stronger anti-distillation protections.
- **Availability:** Fable 5.2 available on major cloud platforms as `claude-fable-5-2`. Mythos access via verification program for cyber/life sciences researchers.

## Significance for AI Founders

Major capability jump for coding agents — 90%+ of Anthropic's own codebase changes now written by Claude is a strong signal. The 30% speed improvement and reduced false-positive safeguards are meaningful for production deployments. Mythos 5.2's sandbox escape rate drop (39% → 3.1%) shows rapid progress on agentic safety.
