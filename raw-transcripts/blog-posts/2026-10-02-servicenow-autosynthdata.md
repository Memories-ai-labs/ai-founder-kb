# AutoSynthData: Generating Training Data for Enterprise Agents
# Author: Esakkivel Esakkiraja, Shruthan Radhakrishna, Denis Akhiyarov, Sagar Davasam (ServiceNow AI)
# URL: https://huggingface.co/blog/ServiceNow-AI/autosynthdata
# Date: 2026-10-02
# Source: Hugging Face Blog / ServiceNow AI Research

## Summary

ServiceNow AI Research releases AutoSynthData, a system for automatically converting model failures into targeted synthetic training datasets for enterprise agents.

## Core Innovation

Curriculum learning strategy: targets tasks "the target model solves on no more than one of three trials" — synthetic data generated addresses genuine capability gaps, not already-mastered tasks.

## Two-Phase Generation Pipeline

1. **Target phase:** Creates core training samples grounded in identified capability gaps
2. **Multiply phase:** Expands accepted samples into variants anchored to vetted originals

## Quality Assurance

Multi-level verification:
- Positive checks (does reference solution work?)
- Negative verification (do incorrect outcomes fail?)
- Repair loops before sample acceptance

## Results on EnterpriseOps Gym

Using Gemma-4-26B-A4B-it as target model:

| Domain | Improvement | Relative Gain | Gap Closed |
|--------|-------------|---------------|------------|
| Hybrid | +7.2pp Pass@1 | 35% relative | 59% of baseline-to-reference gap |
| ITSM   | 18.77% → 27.18% Pass@1 | — | — |

## Significance

Practical approach for fine-tuning enterprise agents without manually curating training data — identifies weaknesses and generates targeted fixes automatically.
