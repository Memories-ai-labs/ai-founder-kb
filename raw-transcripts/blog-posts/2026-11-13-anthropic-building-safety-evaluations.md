# Building strong safety evaluations
# URL: https://www.anthropic.com/research/building-strong-safety-evaluations
# Date: 2026-11-13
# Source: Anthropic Research

Authors: Ruth Appel, Evan Frondorf, Jeremy Hadfield, Rebecca Hiscott, Kamya Jagadish, Shayne Longpre, Madeleine Tucker, Brett Wittmershaus

## Summary

Anthropic publishes recommendations for building, running, and reporting AI safety evaluations — tests that assess whether a model responds appropriately to given inputs.

Key arguments:
- Safety claims are only as reliable as the evaluations behind them. Evals can be gamed, measure the wrong thing, or be hard to reproduce.
- Teams need both domain experts (e.g., clinicians, security researchers) and methods experts to design valid evals.
- Choosing the right measure matters: refusal is often the wrong target. For suicide-related content, for example, refusing to engage can itself be harmful.
- Multi-turn simulations better capture real-world interaction than single-turn prompts.
- AI graders (LLM-as-judge) must be validated against human judgment before being trusted.
- Reporting must include uncertainty estimates, full configuration details, and responsible disclosure of serious flaws.

## Significance for AI founders

As AI products deploy in high-stakes domains (health, finance, legal), rigorous safety evaluation methodology becomes a differentiator. This provides a practical framework for teams building eval pipelines for their own models or for demonstrating safety to enterprise customers and regulators.
