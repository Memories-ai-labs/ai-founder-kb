# Open-sourcing AstaBrief, the fast report-generation model in Asta
# URL: https://huggingface.co/blog/allenai/astabrief
# Date: 2026-10-02
# source: HuggingFace Blog / Allen Institute for AI (Ai2)

Author: Kyle Wiggers (Ai2Comms) et al.

## Summary

Allen Institute for AI releases AstaBrief 8B, an open-weights language model for scientific report generation. The 8B-parameter model transforms research questions and literature excerpts into cited reports ~3.5x faster than proprietary alternatives.

## Development Approach

Built using supervised fine-tuning and direct preference optimization (not RL), prioritizing operational simplicity and data quality:
- Training: 90,000 real researcher queries → filtered to 47,000 supervised examples
- Preference optimization: 6,000 curated comparison pairs evaluated by multiple judge models

## Critical Innovation

Single-pass complete report generation (vs. section-by-section), eliminating expensive intermediate processing. Key finding: simple citation-density filtering outperformed elaborate data quality measures — reports demonstrating consistent evidence grounding beat complex filters.

## Performance

On SQABench-CS2: competitive with Claude-powered systems across rubric scores, answer precision, citation precision, and citation recall. In Asta production: ~41% of Fast mode users continued using it regularly.

## Broader Impact

Open-sourced weights and training data allow local deployment, enabling analysis of sensitive or unpublished work without external API dependencies.
