# Introducing Shieldstral
# URL: https://mistral.ai/news/shieldstral/
# Date: 2026-08-04
# Source: Mistral AI News

## Summary

Shieldstral is a 3B open-weights multimodal safety classifier released by Mistral AI under Apache 2.0. It outperforms models up to 7x its size by framing content moderation as a policy-adaptive question-answering task. Released as an inaugural member of the Open Secure AI Alliance with NVIDIA.

## Core Innovation

Unlike traditional guardrail models that bake fixed harm taxonomies into weights, Shieldstral accepts plain-language policies at inference time. This unifies text and image safety evaluation without retraining.

**Interface:** Three-part request:
- `<Instruct>` — evaluation context, strictness, optional unsafe content definition
- `<Query>` — binary yes/no question (e.g. "Does this content promote physical violence?")
- `<Document>` — content to judge: prompt, response, prompt-response pair, or image with optional text

At inference, reads only `yes` and `no` logits, softmax-normalizes into a continuous safety score.

## Key Properties

- **Adaptive:** Single natural-language interface covers text, image, text+image across prompts/responses/pairs
- **Policy-flexible:** Policies supplied as free-form queries, re-targeted at inference time, no retraining
- **Small:** 3B params, runs on single 16GB NVIDIA GPU
- **Continuous score:** Calibrated yes/no probability from single forward pass
- **Open:** Apache 2.0 weights

## How It Beats Larger Models

**Data strategy — four problems solved:**

1. **Unified heterogeneous data.** Public safety datasets disagree on taxonomies and labels. Converted to same instruction-query-document format with per-dataset processors. Varied wording to prevent overfitting to one style. Calibrated strictness per source.

2. **Discrimination, not memorization.** Constructed sets of deliberately similar, easily confused policies. Asked LLM to rewrite safe text into contrastive pairs — each rewrite violates one policy but not its sibling. Trains the model to distinguish which specific policy content violates (transfers to novel policies at inference).

3. **Grounded safety in images.** Supplemented limited moderation datasets with general-purpose image datasets as negatives. Mutated queries for augmentation. Filtered via vision-language reranker to reduce mislabeled data.

4. **Merged complementary checkpoints.** Fine-tuned with LoRA, merged via SLERP: public-data calibrated checkpoint + fine-grained policy discrimination checkpoint + base instruct model.

**Built on Forge** — Mistral's internal platform for training, aligning, and evaluating custom models.

## Benchmarks vs. Models up to 7x Larger

Evaluated across:
- Text safety
- Refusal detection
- Policy adaptability
- Multimodal safety

Matches or outperforms all tested open guard models up to 7x its size.

## What's Next

Multilingual coverage, longer-document robustness, broader multimodal safety.
