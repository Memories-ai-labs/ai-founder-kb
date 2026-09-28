# Pre-training a 1.11B LLM on a 6 GB Laptop GPU — Measured, Not Claimed
# URL: https://huggingface.co/blog/RitishReal/1b-petrain-llm-in-4gb-vram
# Date: 2026-09-26
# Source: Hugging Face Blog

**Author:** Rambarun Komaljeet

## Key Technical Achievement

Demonstrates a practical method for pretraining a billion-parameter language model on consumer-grade laptop hardware (RTX 4050, 6GB VRAM). Achieved approximately 1,579 tokens/second throughput while operating at "100.6% of the card's measured GEMM peak."

## Core Technical Stack (5 Optimization Techniques)

1. **Block-coordinate descent (BAdam)** — reduces optimizer state storage by ~8×
2. **CPU weight offload** — moves inactive model blocks to system RAM
3. **Ternary quantization (BitNet b1.58)** — compresses weights to {-1, 0, +1} values
4. **Tied embeddings** — shares vocabulary table between input and output layers
5. **Gradient checkpointing** — trades computation for memory by recomputing activations

## Realistic Timeline

Despite fitting the model in 6GB, pretraining requires approximately 375 days to complete properly using Chinchilla-optimal token allocation (36 billion tokens). The author emphasizes: "fitting ≠ training," highlighting the distinction between hardware capacity and practical training duration.

## Architecture Details

The model uses a gated DeltaNet hybrid combining recurrent layers with two sliding-window attention layers, enabling "exact token recall" from recent context while maintaining constant-memory inference properties.

## Honest Methodology

The post transparently documents failures, including 11 rejected ideas, 5 withdrawn conclusions, and 8 silent bugs discovered during development — demonstrating rigorous empirical methodology rather than marketing claims.
