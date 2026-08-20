---
Title: Same Cluster, 33 Points More Utilization: What Changed Was the Order
Publisher: Hugging Face (Dharma AI)
URL: https://huggingface.co/blog/Dharma-AI/gpu-management-pt2
Date: 2026-08-17
Source: Hugging Face Blog
---

# Same Cluster, 33 Points More Utilization: What Changed Was the Order

**Date:** August 17, 2026
**Author:** Dharma AI

## Key Achievement

Dharma AI's research demonstrates that GPU utilization improved by up to 33 percentage points on identical hardware using the same workloads—simply by changing job allocation order. Their constraint-aware allocator outperformed traditional FIFO scheduling across seven benchmark scenarios.

## The Core Problem

Two incompatible workload shapes competing for GPU resources:

- **Batch-like work** (training, batch inference, quantization): requires contiguous GPU blocks held without interruption
- **Real-time inference**: elastic demand that fluctuates throughout the day

Traditional FIFO schedulers handle this poorly by reserving peak capacity all day, leaving GPUs idle during low-traffic periods.

## The Solution

Rather than static reservations, the allocator treats real-time demand as a dynamic curve and schedules batch jobs by priority across a 24-hour planning horizon. The system encodes five structural constraints directly into its decision logic, ensuring every allocation is valid by design.

## Results Snapshot

| Scenario | Utilization Gain | Value Improvement |
|----------|-----------------|------------------|
| Training-heavy | 53.6% → 87.0% | +105.1% |
| Mixed control | 51.6% → 72.4% | +54.8% |
| Scale test (64 GPUs) | No change | +15.9% |

The scale test particularly matters—it shows gains persist at production size with 15ms latency.
