# Training and Finetuning Multi-Vector Embedding Models with Sentence Transformers
# URL: https://huggingface.co/blog/train-multi-vector-encoder
# Date: 2026-08-26
# Source: Hugging Face Blog

Authors: Tom Aarsen, adaamko, yjoonjang, MichelleRuwen, paulomouraj

## Overview

This post introduces Sentence Transformers v6.0's `MultiVectorEncoder` for ColBERT-style late interaction retrieval. It demonstrates how to finetune multi-vector models that outperform general-purpose retrievers on domain-specific data.

## Key Findings

The author trained a medical retrieval model (mLateOn-medical) achieving **0.9139 NDCG@10** on the MIRIAD benchmark — outperforming all evaluated models including dense embeddings like Qwen3-Embedding-4B (0.7817) and zero-shot multi-vector models (0.8520).

### Training Performance
- **Duration:** 14.5 hours on a single RTX 3090
- **Data:** 1 million medical question-passage pairs
- **Improvement:** +0.062 NDCG@10 versus the strongest zero-shot competitor

## Critical Training Components

**Model Selection:** Unsupervised checkpoints adapted better than fully supervised ones. "The `-unsupervised` checkpoints adapt to a new domain far better than their finished siblings."

**Loss Function:** `CachedMultiVectorMultipleNegativesRankingLoss` uses in-batch negatives with memory-bounded chunks, enabling larger effective batch sizes.

**Document Length:** Most released models truncate at 180-512 tokens, but medical passages average 941 tokens. Removing these caps improved performance measurably.

## Index Optimization

Token pooling and 1-bit PLAID quantization reduced index size from 45 GB to 1.45 GB while maintaining strong NDCG@10 scores (0.8642), making multi-vector retrieval competitive with dense models on storage.

## Practical Takeaway

Domain-specific finetuning on modest data (100k pairs in ~75 minutes) yields substantial retrieval improvements, making custom multi-vector models accessible on consumer GPUs.
