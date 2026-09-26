# Bringing Humanoids to LeRobot
# URL: https://huggingface.co/blog/nepyope/bringing-humanoids-to-lerobot
# Date: 2026-09-25
# source: Hugging Face Blog

## Authors
Martino Russi, Steven Palma, Pepijn Kooijmans, Khalil Meftah, Maxime Ellerbach, and 7 others

## Overview

LeRobot (open-source Python library for robot learning) integrates humanoid robots, specifically the Unitree G1. Complete workflow from teleoperation demonstrations to policy training.

## Key Technical Approach

Two-tier architecture:
- A learned policy predicts "SONIC latent motion tokens" from language, camera observations, and robot state
- A fast controller decodes tokens into 29-degree-of-freedom whole-body motion

As authors explain: "a biped must balance continuously while walking, reaching, and responding to disturbances" — requiring separation between learned policy and low-level control.

## Notable Achievements

- Fine-tuned policy on ~100 episodes (71 minutes of data) for can pick-and-place tasks
- Ball-dodging: 79.1% success rate in simulation
- Released open-source hardware: Homunculus exoskeleton and glove for teleoperation
- Published HIW-500 dataset: 500+ hours and 23K episodes of real-world G1 demonstrations

## Next Steps

Plan to support ASIMOV (open-source humanoid from Menlo Research), broader goal to unify humanoid robotics tools and data within LeRobot.

## Significance for AI Founders

Open-source robotics foundation models are maturing rapidly. The combination of cheap teleoperation hardware + open datasets + policy fine-tuning pipelines dramatically lowers the barrier to entry for robotics startups.
