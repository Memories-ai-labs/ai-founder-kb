# Introducing Olmo-core 3: Open, scalable training infrastructure for large MoEs
# Author: Kyle Wiggers (Ai2Comms) / Allen Institute for AI
# URL: https://huggingface.co/blog/allenai/olmocore3
# Date: 2026-10-01
# Source: Hugging Face Blog / Allen AI

## Summary

AllenAI releases Olmo-core 3, a fully open-source training infrastructure framework for large Mixture-of-Experts (MoE) models.

## Key Technical Contributions

**Architecture Redesign:**
- Shifted from FSDP (fully sharded data parallelism) to DDP (distributed data parallelism)
- Experts remain resident on GPUs rather than repeatedly gathering weights
- Achieved 2.7x throughput vs. prior implementation

**Scaling Efficiency:**
- Expert pool scaling: 8 → 128 experts while maintaining ~3.2B active parameters per token
- Less than 5% throughput reduction at this scale

**Three Parallelism Techniques:**
1. Expert parallelism — distributes specialist components across GPUs
2. Pipeline parallelism — splits model layers across GPU groups
3. Distributed optimizer — reduces memory demands per device

**Performance Optimizations:**
- Rowwise expert parallelism, GPU-resident routing, grouped GEMM operations
- MXFP8 lower-precision format: ~21% throughput gain vs. BF16

**Scale Demonstrated:**
- 1.2T total parameters across 512 GPUs
- Exploratory work up to 2.38T parameters

## Significance

Enables trillion-parameter MoE training as open-source infrastructure, democratizing access to techniques previously limited to hyperscalers.
