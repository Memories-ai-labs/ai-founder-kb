# EVA-Bench Data 2.0: 3 Domains, 121 Tools, 213 Scenarios
# URL: https://huggingface.co/blog/ServiceNow-AI/eva-bench-data
# Date: 2026-06-04
# Source: Hugging Face Blog (ServiceNow AI)

**Authors:** Tara Bogavelli, Gabrielle Gauthier Melancon, Katrina Stankiewicz, Nifemi Bamgbose, Fanny Riols, Hoang Nguyen, Raghav Mehndiratta, Lindsay Brin, Joseph Marinier, Hari Subramani, Anil Madamala, and ServiceNow-AI team

## Overview

ServiceNow-AI released an expanded version of EVA-Bench, an evaluation framework for voice agents. The update scales the benchmark from a single domain to three enterprise sectors: Airline Customer Service Management (50 scenarios), Enterprise IT Service Management (80 scenarios), and Healthcare HR Service Delivery (83 scenarios). Combined, they provide "213 evaluation scenarios across 121 tools, a roughly 4x increase in scenario coverage from our original release."

## Key Design Principles

The datasets follow five foundational principles:

**Voice-first approach:** Only tasks typically handled via phone are included, ensuring realistic call patterns.

**Authenticity:** Tool schemas mirror production APIs, and policies reflect actual enterprise constraints, including healthcare regulations.

**Diversity:** Scenarios span single-intent calls, multi-intent conversations with up to four objectives, and adversarial cases where users attempt unauthorized actions.

**Authentication focus:** Every domain incorporates authentication mechanisms calibrated to real-world deployments.

**Reproducibility:** Each scenario has "exactly one correct resolution path," eliminating evaluation ambiguity.

## Generation and Validation

Scenarios are created using SyGra, a graph-based synthetic data generator powered by GPT-5.4. Three components are generated jointly:

- Structured user goals (decision trees specifying caller behavior)
- Initial scenario databases with consistent entities
- Expected final database states serving as ground truth

The process includes multi-stage validation: structural checks via Pydantic schemas, LLM-based consistency verification, and trace verification ensuring policy compliance.

All scenarios underwent manual review and were validated against three frontier models: OpenAI GPT-5.4, Google Gemini 3.1 Pro, and Anthropic Claude Opus 4.6. Any zero-scored scenarios were manually investigated for dataset issues.

## Multilingual Expansion

The team is adapting the benchmark for multiple languages, customizing not just conversation text but also location names, user identities, and phone number formats to reflect authentic regional contexts.

## Accessibility

The dataset, evaluation framework, and leaderboard are open-source under the MIT license. Data loads directly via Hugging Face's datasets library using domain-specific configuration parameters.
