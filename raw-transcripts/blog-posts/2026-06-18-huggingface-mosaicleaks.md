# MosaicLeaks: Can your research agent keep a secret?

Title: MosaicLeaks: Can your research agent keep a secret?
Publisher: Hugging Face (ServiceNow Research)
Authors: Alexander Gurung, Rafael Pardinas, and collaborators at ServiceNow
URL: https://huggingface.co/blog/ServiceNow/mosaicleaks
Date: 2026-06-18
Source: Hugging Face Blog

---

## Overview

The article examines how research agents combining private enterprise documents with external web search tools create unintended privacy vulnerabilities. The core issue: while individual web queries may seem innocuous, their cumulative pattern can leak sensitive corporate information through what researchers call the "mosaic effect."

## Key Problem

The research highlights three escalating leakage categories:

- **Intent leakage:** Observers deduce what private questions the agent investigates
- **Answer leakage:** Query logs contain enough information to answer private questions
- **Full-information leakage:** Observers can state verifiable private facts without being told what to seek

The MediConn example illustrates this: separate searches about cloud migration, January 2024 security disclosures, and affected vendors individually seem harmless but collectively reveal that MediConn completed 70% infrastructure migration by January 2025.

## Proposed Solution: PA-DR

The authors introduce **Privacy-Aware Deep Research (PA-DR)**, combining two training rewards:

1. **Situational task reward** — judges each decision against comparable decisions at identical workflow stages rather than scoring entire trajectories
2. **Learned privacy reward** — classifies whether queries leak private information directly or create mosaic vulnerabilities

## Results

Training with PA-DR achieved notable improvements:
- Maintained strict chain success at 58.7% (down only slightly from 59.3% with task-only training)
- Reduced answer/full-information leakage from 34.0% to 9.9%
- Required 5-6x fewer training samples than traditional outcome-based approaches

Interestingly, the agent issued *more* web queries than baseline but removed revealing specific details like metrics or dates.

## Limitations

The researchers acknowledge MosaicLeaks as a controlled benchmark using synthetic enterprise documents and fixed web corpora — not a measurement of real-world deployed systems.
