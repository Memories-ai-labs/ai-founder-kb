# Hugging Face and Cerebras Bring Gemma 4 to Real-Time Voice AI
**Source:** Hugging Face Blog
**URL:** https://huggingface.co/blog/cerebras-gemma4-voice-ai
**Date:** 2026-07-01
**Authors:** Amir Mahla, Andres Marafioti, Leandro von Werra, Saurabh Vyas, Cerebras team, 34+ contributors

---

## Summary

Hugging Face and Cerebras demonstrate a real-time speech-to-speech AI system that achieves natural conversation latency using an open-source, modular pipeline. The article addresses the core challenge in voice AI: response delays that break conversational flow.

## Technical Architecture

Modular open-source pipeline:
- **STT:** NVIDIA Parakeet (speech recognition)
- **LLM:** Google DeepMind Gemma 4 31B (running on Cerebras inference infrastructure)
- **TTS:** Alibaba Qwen3TTS (text-to-speech synthesis)

Key insight: "Latency is a critical parameter" — Cerebras provides the inference speed that makes sub-second responses possible.

## Deployment

Already deployed in 9,000+ Reachy Mini robots (embodied AI application), demonstrating that this isn't a demo — it's production infrastructure.

## Significance

- First major HF+Cerebras collaboration for voice AI
- Uses Gemma 4 31B (DeepMind's open model) as the LLM backbone — not proprietary
- Fully open-source pipeline: anyone can replicate with HF Spaces demo + speech-to-speech GitHub repo
- Demonstrates that real-time voice AI is now achievable with open models + fast inference, without needing proprietary APIs

## Resources

- Demo: Hugging Face Spaces
- Code: huggingface/speech-to-speech repository
