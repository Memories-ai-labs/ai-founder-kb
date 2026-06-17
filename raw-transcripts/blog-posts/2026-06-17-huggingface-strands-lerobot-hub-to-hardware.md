---
Title: From the Hugging Face Hub to Robot Hardware with Strands Agents and LeRobot
Authors: Sundar Raghavan, Cagatay Cali (AWS)
Date: 2026-06-17
Source: Hugging Face Blog
URL: https://huggingface.co/blog/amazon/strands-lerobot-hub-to-hardware
Publisher: Hugging Face / Amazon Web Services
---

# From the Hugging Face Hub to Robot Hardware with Strands Agents and LeRobot

**Published:** June 17, 2026
**Authors:** Sundar Raghavan (AWS), Cagatay Cali (AWS)

## Overview

This article demonstrates how to integrate LeRobot with Strands Robots SDK to create a unified workflow connecting AI models from Hugging Face Hub directly to physical robot hardware. The integration enables developers to record demonstrations, train policies, run simulations, and deploy to real robots using a single agent-based interface.

## Key Capabilities

The workflow accomplishes five core tasks within a single agent loop:

1. **Recording demonstrations** in MuJoCo simulation that generate LeRobotDatasets matching the format of hardware-recorded data
2. **Pushing datasets** to the Hugging Face Hub for sharing and training
3. **Running policies** in simulation using GR00T, LerobotLocal, or Mock providers
4. **Deploying identical code** to physical SO-101 robots with a single parameter change (`mode="real"`)
5. **Coordinating fleets** across multiple robots using a Zenoh-based peer mesh

## Design Philosophy

The integration maintains a deliberately minimal wrapper approach. "Strands Robots doesn't reimplement what LeRobot already provides." Hardware abstraction, calibration, and dataset formats remain in LeRobot's domain, while Strands adds the AgentTool abstraction layer enabling natural language composition.

## Technical Highlights

**Unified Dataset Format:** Datasets recorded in simulation and on physical hardware use identical on-disk structures (parquet + MP4 layout), allowing training scripts to consume both interchangeably without modification.

**Policy Agnostic:** The system supports multiple inference backends—NVIDIA's GR00T, in-process LerobotLocal (ACT, Diffusion Policy, SmolVLA, π0, π0.5), and NVIDIA Cosmos 3—all accessible through a consistent interface.

**Minimal Requirements:** The default simulation path requires only Python 3.12+, a model provider (Bedrock, Anthropic API, OpenAI, or Ollama), and the installed SDK. No GPU, Docker, or Hugging Face credentials needed for basic operation.

## Security Considerations

Three critical safeguards for production use:

- **Prompt injection mitigation** through careful input validation from trusted sources only
- **Mesh authentication** requiring `STRANDS_MESH_AUTH_MODE=mtls` for untrusted networks (development defaults to no auth)
- **Human-in-the-loop approval** for fleet-wide actions, blocking autonomous execution of broadcast and emergency stop commands

## Getting Started

Installation: `uv pip install "strands-robots[sim-mujoco,lerobot,mesh]"`

Example: `strands-labs/robots` repository at `examples/lerobot/hub_to_hardware.py`

## Resources

- **Strands Robots:** Apache 2.0 licensed SDK at github.com/strands-labs/robots
- **LeRobot:** github.com/huggingface/lerobot (datasets, policies, drivers)
- **Supported Models:** MolmoAct2, π0, SmolVLA, GR00T N1.7, Cosmos3 Nano
