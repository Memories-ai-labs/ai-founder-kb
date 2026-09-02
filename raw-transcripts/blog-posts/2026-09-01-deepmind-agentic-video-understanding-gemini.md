# Introducing Agentic Video Understanding with Gemini
# URL: https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-agentic-video-in-gemini/
# Date: 2026-09-01
# Source: Google DeepMind Blog

Authors: Rohan Doshi (Senior Product Manager, Google DeepMind) and Mario Lučić (Research Director, Google DeepMind)

## Overview

Google has launched agentic video understanding across Gemini 3.7 Flash, 3.6 Flash, and 3.5 Flash-Lite models. This capability enables more efficient video analysis by allowing the model to dynamically scan video segments rather than processing at fixed frame rates.

## Key Performance Metrics

- **Token reduction:** Up to 88% fewer tokens consumed
- **Cost savings:** Up to 66% reduction in analysis costs
- **Accuracy gains:** Up to 7% improvement in accuracy

Gemini 3.7 Flash with agentic understanding achieves the best quality-to-cost ratio among tested models.

## How It Works

Rather than static processing at fixed frame rates, agentic video understanding allows Gemini to actively determine what content to examine, at what speed, and through which modality (visual frames, audio, or transcripts). The model invokes internal tools to load only relevant video segments, reducing development overhead.

## Primary Use Cases

- Sub-second moment retrieval for precise video editing
- Long-form video searching across multi-hour content
- Enhanced anomaly detection through dynamic resampling
- Accurate action and object counting

## Availability and Getting Started

The feature is available via the Gemini API in Google AI Studio and the Gemini Enterprise Agent Platform using standard API pricing with no additional fees. Developers enable it by setting processing to "agentic" in API configuration. Rollout to Gemini app users is coming soon, with YouTube's "Ask YouTube" feature integration planned for the coming months.
