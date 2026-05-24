# #11 — AI Workloads Are Not LLM Workloads / Video Is Compute-Bound

## One-Line Summary

fal: "Video models are compute-bound (LLM is memory-bound) — the optimization paths are completely different." Top-5 video models have a 30-day half-life. Daytona: agent workloads are spiky (15% baseline → 90% bursts). Dylan Patel: GPU economics + the EUV bottleneck.

## Supporting Evidence (Independent Sources)

fal on Sequoia / Daytona on Latent Space / Dylan Patel on Dwarkesh / Sundar Pichai ($180B CapEx + memory crunch) / Sora 2 (diffusion transformer)

## Action Implication for Memories.ai

Redesign the Memories.ai video pipeline (do not copy LLM-serving optimization): (1) compute-saturating architecture, (2) hot-swappable backbones (models turn over every 30 days), (3) billing by burst budget, not req/s, (4) lock multi-year GPU contracts to hedge.

---

← [Patterns index](./README.md) · [→ KB home](../README.md)