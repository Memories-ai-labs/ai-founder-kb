# Async GRPO with LoRA across HF Jobs: a bucket, a proxy, and no NCCL
# URL: https://huggingface.co/blog/asyncgrpo-lora-hfjobs
# Date: 2026-09-10
# Source: Hugging Face

## Summary

Production system for distributed reinforcement learning that separates training and inference across independent Hugging Face Jobs using LoRA adapters and Storage Buckets instead of traditional NCCL communication.

**Authors:** Amine Dirhoussi, Quentin Gallouédec, Kashif Rasul, Sergio Paniego, and 12 contributors

## Key Innovation

Leverages LoRA support in TRL's `AsyncGRPOTrainer` (v1.14). Rather than syncing full model weights (gigabytes), only compact rank-1 adapters (megabytes) transfer between components. A rank-1 adapter for a 1.5B model is ~a few MB vs ~3 GB for the full model.

## Architecture

Three separate Jobs:
- One trainer Job running `AsyncGRPOTrainer` with LoRA
- Two vLLM inference Jobs serving the base model plus adapters
- A Storage Bucket mounted as shared filesystem across all three

Custom routing proxy:
- Adds authentication headers for Job communication
- Routes completion requests to replicas holding relevant KV cache
- Broadcasts adapter updates to all inference servers

## Performance Results

Five experimental iterations reduced runtime from 3h 27min to 53min for 500 training steps (3.9x speedup). Key optimizations:
- Token-budget batching (dense sequence packing)
- Disabling gradient checkpointing for memory efficiency
- Increasing concurrent in-flight requests

Policy version alignment ("ratio") stayed between 0.9993–1.0004 across 126 adapter syncs, proving correctness.

## Validation

Used "Sanity" dataset: 1,460 MATH problems for RL validation. Reward improved from 0.145 to 0.438 over the run.

## Practical Takeaway

Distributed RL training across independent cloud instances is viable without specialized cluster infrastructure — opens accessible large-scale RL experimentation for teams without bespoke GPU clusters.
