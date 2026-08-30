# Intelligent transcription with Gemini 3.5 Transcribe
# URL: https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-5-transcribe/
# Date: 2026-08-26
# Source: Google Blog

Authors: Diego Melendo Casado (Senior Director, Engineering, Gemini Audio) and Luke Leonhard (Chief of Staff, Gemini Audio)

## Overview

Google introduced Gemini 3.5 Transcribe, described as "our most precise speech-to-text model yet, designed for intelligent voice interactions." The model converts raw audio into accurate, polished, formatted text and handles background noise, complex terminology, and automatic cleanup of speech irregularities.

## Key Capabilities

- Smart transcription: handles self-corrections, removes filler words
- Function calling: delegates complex tasks to other Gemini models
- Custom vocabulary recognition for specialized jargon
- 85+ language support with automatic detection
- Multi-speaker identification with timestamps (up to 3 speakers)

## Performance

- Streaming Word Error Rate (WER): 4.0%
- Non-streaming WER: 2.6%
- 70% improvement in time to final transcription vs. prior model (Chirp 3)

## Availability

- Public preview via Gemini API in Google AI Studio
- Real-time streaming through the Live API
- Pre-recorded audio via the Interactions API
- Consumer: Rambler feature on Gboard (Android), Gemini macOS app, Chrome (coming soon)

## Integration Ecosystem

Integrated with Agora, LangChain, LiveKit, Pipecat, and Vercel for voice-driven app development.
