# LeRobot v0.6.0: Imagine, Evaluate, Improve
# Publisher: HuggingFace
# URL: https://huggingface.co/blog/lerobot-release-v060
# Date: 2026-07-07
# source: HuggingFace Blog

## Overview

Major LeRobot release advancing robot learning with world model policies that predict future states, reward models for success detection, deployment tools with human-in-the-loop correction, and six simulation benchmarks.

## New Policy Architectures (World Models)

**VLA-JEPA:** Compact vision-language model that anticipates future frames in latent space; world model disappears at inference (no overhead). DROID-pretrained base checkpoint available for fine-tuning.

**LingBot-VA:** Autoregressive video-action model predicting future frames and actions sequentially; reincorporates real observations to maintain grounding.

**FastWAM:** Questions whether test-time future imagination is necessary — combines video-generation with action expert producing action chunks directly without dreaming at inference.

## VLA Ecosystem (5 new models)

- **GR00T N1.7:** NVIDIA's upgraded cross-embodiment foundation model (Cosmos-Reason2-2B)
- **MolmoAct2:** Allen Institute's model with zero-shot deployment capabilities
- **EO-1:** Qwen2.5-VL-3B backbone with flow-matching
- **Multitask DiT:** ~450M diffusion transformer for language-conditioned multi-task learning
- **EVO1:** Compact 0.77B model with real-time chunking support

## Reward Models

**Robometer:** Pretrained general-purpose reward model (Qwen3-VL-4B), trained on 1M+ robot trajectories; scores task progress without task-specific training.

**TOPReward:** No reward weights needed; reads log-probabilities from standard VLMs given trajectory video and task instructions.

## Evaluation: 6 New Benchmarks

- LIBERO-plus: ~10,000 perturbed LIBERO variants
- RoboTwin 2.0: 50 bimanual tasks (100k+ training trajectories)
- RoboCasa365: 365 kitchen tasks across 2,500 procedurally generated environments
- RoboCerebra: Long-horizon tasks chaining 3-6 sub-goals
- RoboMME: Memory evaluation (counting, tracking, procedure imitation)
- VLABench: Knowledge and reasoning tests

## Deployment

**lerobot-rollout CLI:** Replaces ad-hoc deployment scripts with DAgger-style human-in-the-loop correction.

**FSDP Training:** Fully sharded data parallel support; **HF Jobs Integration** for cloud training (`--job.target=a10g-small`).

## Infrastructure

- Base installation reduced ~40% with feature-scoped extras
- PyTorch 2.7–2.11 support, CUDA 12.8 wheels
- Depth camera support (Intel RealSense), VLM-powered dataset annotations
- LeLab: browser-based UI for full workflow without CLI
