# Eyas — AI Security Camera Agent

**Title**: Eyas — AI Security Camera Agent
**Publisher**: Hugging Face (Build Small Hackathon — Seunghyun, Hanhee Lee, Javier Huang)
**URL**: https://huggingface.co/blog/build-small-hackathon/eyas
**Date**: 2026-06-15
**Source**: Hugging Face Blog (Community / Hackathon)

---

## Overview

Eyas is an offline CCTV intelligence system designed to help small business owners detect suspicious activity in real-time. Built for the Build Small Hackathon, it processes security footage locally using a chain of compact models without requiring cloud APIs.

## Motivation

The project emerged from a teammate's family experience running a retail shop. Shoplifting is a persistent problem, but traditional CCTV review is reactive — footage is checked only after theft occurs. Eyas enables immediate alerts so staff can respond during an incident.

## Technical Architecture (4-Stage Pipeline)

1. **YOLO11n + BotSORT** — Detects and tracks people across frames (6 MB model)
2. **MiniCPM-V 4.6** — Analyzes tracked individuals, outputs structured JSON observations (1.3B parameters)
3. **Heuristic Structurer** — Converts observations into typed events with timestamps
4. **Nemotron 3 Nano 4B** — Reasons over event logs, generates summaries and answers queries

Additional: TinyAya for Korean translation; VoxCPM2 for text-to-speech.

## Key Technical Insights

- **YOLO11n** processes frames in 30–80ms on CPU; 4 frames per tracked person selected (entry, mid-dwell, exit)
- **MiniCPM-V** proved effective despite no CCTV training data — describes suspicious actions conservatively rather than hallucinating
- **The heuristic layer** (not model upgrades) had the greatest impact on quality — models needed careful event-emission logic
- **Nemotron 3 Nano 4B** runs at 12–18 tokens/second on M-series Mac; grammar-constrained JSON = reliable structured output
- A 30-minute clip processes in 8–12 minutes on CPU — acceptable for morning footage review

## Key Lesson for AI Builders

> "Small models proved honest about uncertainty rather than confident in errors. The heuristic layer — not model upgrades — had the greatest impact on quality."

This is a reusable insight for multi-model pipelines: non-ML logic connecting model stages often dominates system performance.

## Resources

- [Live Demo](https://huggingface.co/spaces/build-small-hackathon/eyas)
- [Source Code](https://huggingface.co/spaces/build-small-hackathon/eyas/tree/main)
