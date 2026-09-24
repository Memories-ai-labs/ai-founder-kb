# How to Use NVIDIA Warp and MjWarp to Accelerate Robotics Simulation and Learning Workflows
# URL: https://huggingface.co/blog/nvidia/how-to-use-nvidia-warp-and-mjwarp
# Date: 2026-09-23
# Source: Hugging Face Blog

**Published:** September 23, 2026
**Authors:** Johnny Nuñez Cano, Asier Arranz, Rishabh Chadha, Ben Oliveri (NVIDIA)

---

This blog post, the second in NVIDIA's "State of Simulation for Physical AI" series, explores GPU acceleration for robot simulation using NVIDIA Warp and MuJoCo Warp (MJWarp). The article demonstrates migrating an SO-101 robotic arm from CPU-based MuJoCo to GPU-accelerated MJWarp, scaling from single environments to 2,048 parallel worlds.

## Key Concepts

**NVIDIA Warp** is described as "a Python framework for writing high-performance, GPU-accelerated kernels." It enables developers to author statically-typed kernels in Python that compile to CUDA or CPU code, supporting differentiability and deterministic execution.

**MuJoCo Warp (MJWarp)** implements MuJoCo's physics pipeline on Warp, enabling "batched GPU throughput" for multiple independent simulation environments simultaneously, rather than optimizing single-environment latency.

## Core Distinction

The authors emphasize a critical measurement difference: "latency is wall-clock time for one simulation step" while "aggregate throughput is the total number of world-steps completed per measured wall-clock second." MJWarp prioritizes throughput, benefiting reinforcement learning and large-scale sampling scenarios.

## Migration Workflow

The article outlines five validation gates:

1. Establish MuJoCo CPU baseline with an SO-101 pick-and-place task
2. Validate single-world MJWarp parity
3. Size contact and constraint buffer capacity
4. Scale to 2,048 parallel worlds
5. Verify and measure accurately

## Technical Implementation Details

Key parameters for MJWarp allocation include `nworld` (parallel environments), `nconmax` (contacts per world), and `njmax` (constraint limits per world). The authors recommend CUDA Graph capture for performance: "capture once, replay often" to reduce dispatch overhead.

## Validation Requirements

Proper GPU timing requires synchronization: "without this you time the queue, not the work." The article emphasizes warm-up iterations before measurement and explicit buffer synchronization immediately before and after timed regions.

## Integration Path

The article positions MJWarp as foundational for training frameworks. It references upcoming implementations through mjlab, MuJoCo Playground, and Isaac Lab with Newton, indicating a progression toward complete training systems.
