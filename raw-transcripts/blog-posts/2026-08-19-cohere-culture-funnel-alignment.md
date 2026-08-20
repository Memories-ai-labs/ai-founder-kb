---
Title: The Culture Funnel: You can't align what isn't in the data
Publisher: Cohere Labs
URL: https://cohere.com/blog/the-culture-funnel-you-cant-align-what-isnt-in-the-data
Date: 2026-08-19
Source: Cohere Blog
---

# The Culture Funnel: You can't align what isn't in the data

**Date:** August 19, 2026
**Author:** Cohere Labs (Research)

## Overview

Cohere Labs published research demonstrating that cultural diversity significantly narrows as language models progress through training pipelines—a phenomenon they term "the culture funnel."

## Main Findings

### Cultural Loss During Training

The research analyzed 5.6 million training samples and found that "pretraining data has much more cultural grounding...than any post-training dataset." Post-training focuses heavily on technical tasks like coding and mathematics, which contain fewer cultural markers.

### Multilinguality Doesn't Equal Multicultural Representation

Adding more languages increases geographic diversity but doesn't proportionally boost cultural content. The relationship proves "more complicated" than assumed, with scaling multilinguality showing "diminishing returns."

### Geographic Representation Imbalance

Cultural data follows a long-tail distribution, with India, China, and the USA dominating representation. African, South American, and many other regions appear significantly underrepresented in cultural training data.

### Where Culture Matters Most

Users report needing cultural awareness most in:
- Creative writing
- Translation
- Message writing

These tasks already contain stronger cultural signals in training data. However, cultural awareness relevance extends across domains beyond current training distributions.

## Proposed Solutions

Adding explicit cultural markers during fine-tuning (without changing data distribution) improved performance on cultural benchmarks by 2-8% while maintaining general multilingual capabilities.
