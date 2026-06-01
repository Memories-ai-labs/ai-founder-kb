# Welcome NVIDIA Cosmos 3: The First Open Omni-model for Physical AI Reasoning and Action
# URL: https://huggingface.co/blog/nvidia/cosmos-3-for-physical-ai
# Date: 2026-06-01
# Source: HuggingFace Blog (NVIDIA)

## Overview

NVIDIA Cosmos 3 is the first open omni-model for physical AI reasoning and action. It combines world generation, physical reasoning, and action generation in a single unified model—eliminating the need to juggle multiple separate models.

## Key Innovations

**Architecture**: Built on Mixture-of-Transformers (MoT) that processes text, image, video, audio, and action modalities in one unified architecture. Uses separate autoregressive (AR) and diffusion (DM) subsequences that interact through joint attention.

**Previous vs. New Approach**:
- Old: Separate models (Cosmos Predict, Cosmos Transfer, Cosmos Reason, Cosmos Policy)
- New: Single omni-model handling all capabilities

## Model Versions

1. **Cosmos 3 Nano** (8B parameters) — Optimized for efficient inference on workstation-grade GPUs like RTX PRO 6000
2. **Cosmos 3 Super** (32B parameters) — For large-scale synthetic data generation and research

## Core Capabilities

| Input | Output | Application |
|-------|--------|------------|
| Text/Image/Video | Video | Video Generation |
| Text/Video | Text | Vision Language Model |
| Action/Image/Text | Video | Forward Dynamics |
| Text/Video | Action | Inverse Dynamics |
| Image/Text | Video & Action | Policy Model |

## Use Cases
- Robotics (pick-and-place tasks)
- Autonomous vehicles (long-tail driving scenarios)
- Warehouse safety
- Smart spaces

## Integration with Diffusers

```python
import torch
from diffusers import Cosmos3OmniPipeline

pipe = Cosmos3OmniPipeline.from_pretrained(
    "nvidia/Cosmos3-Nano", torch_dtype=torch.bfloat16, device_map="cuda"
)

result = pipe(prompt="your prompt", num_frames=1, height=720, width=1280)
result.video[0].save("output.jpg")
```

## Datasets Released
NVIDIA released six synthetic data generation (SDG) datasets:
- Embodied-Robot-Scenes
- Physical-Interaction-Scenes
- Spatial-Reasoning
- Digital-Human-Scenes
- Autonomous-Driving-Scenarios
- Warehouse-Operations-Scenes

## Key Resources
- GitHub: https://github.com/NVIDIA/Cosmos-Framework
- Models: nvidia/Cosmos3-Nano and nvidia/Cosmos3-Super (HuggingFace)
- Technical paper: https://research.nvidia.com/labs/cosmos-lab/cosmos3/technical-report.pdf
