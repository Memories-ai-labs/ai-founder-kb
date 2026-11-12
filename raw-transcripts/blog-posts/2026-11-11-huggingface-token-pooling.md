# Token Pooling-Aware Training for Multi-Vector Embedding Models
# URL: https://huggingface.co/blog/token-pooling
# Date: 2026-11-11
# Source: Hugging Face Blog

Author: Tom Aarsen (tomaarsen)
Published: November 11, 2026

## Overview
Multi-vector models like ColBERT store many vectors per document, which becomes expensive at corpus scale. Token pooling merges similar vectors to reduce storage, but aggressive merging can discard useful information. This post presents pooling-aware training to close that gap.

## Key Concepts

**HierarchicalTokenPooling**: Uses Ward clustering to merge token vectors. Budget is controlled via `pool_factor`, `max_tokens`, or `distance_threshold`.

**Pooling-aware training**: Adds a second loss computed on pooled document representations, averaged with the standard retrieval loss. Implemented via `MultiVectorTokenPoolingLoss` in Sentence Transformers.

## Results
On NanoBEIR at `pool_factor=4`:
- Standard model: retains 94.6% of unpooled nDCG@10
- Pooling-aware model: retains 97.8%, with 74.8% fewer document vectors

## Practical Benefits
- Significant storage reduction with minimal retrieval quality loss
- Optional kernels accelerate MaxSim scoring and clustering
- Combines well with embedding quantization and Matryoshka embeddings for further compression

## Significance
Practical solution for deploying multi-vector retrieval models (ColBERT-style) at scale without paying the full storage cost. Addresses the core production constraint for dense retrieval systems.
