# Gemma 4 12B: A Unified Multimodal Model
# URL: https://blog.google/innovation-and-ai/technology/developers-tools/introducing-gemma-4-12b/
# Date: 2026-06-03
# Source: Google (blog.google)

Authors: Olivier Lacombe (Director of Product Management, Google DeepMind) and Gus Martins (Product Manager, Google DeepMind)
Published: June 3, 2026

## Key Highlights

Google announced Gemma 4 12B, a mid-sized AI model designed to deliver advanced multimodal capabilities on consumer laptops. Bridges between Google's edge-friendly E4B and the more powerful 26B Mixture of Experts variant.

## Core Features

**Unified Architecture:** Unlike traditional multimodal models that use separate encoders, Gemma 4 12B processes visual and audio inputs directly through its language model backbone. Vision processing relies on "a lightweight embedding module consisting of a single matrix multiplication, positional embedding and normalizations," while audio signals project directly into the same space as text tokens.

**Performance & Efficiency:** Delivers benchmark results approaching the 26B MoE variant while requiring less than half the memory footprint, enabling local operation on machines with 16GB of RAM.

**Native Audio Support:** First mid-sized Gemma model to feature native audio input capabilities.

## Availability & Integration

Released under Apache 2.0 licensing. Accessible through Hugging Face, Kaggle, Ollama, and LM Studio. Development support via documentation, quick-start notebooks, and a skills repository for agent development.
