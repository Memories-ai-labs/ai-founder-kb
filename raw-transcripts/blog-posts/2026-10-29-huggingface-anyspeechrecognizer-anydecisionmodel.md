# Introducing AnySpeechRecognizer and AnyDecisionModel: Open Models for Speech and Decisions on Apple Platforms
# URL: https://huggingface.co/blog/anydecisionmodel
# Date: 2026-10-29
# Source: Hugging Face Blog

Author: Mattt (Hugging Face)

Two Swift packages for Apple platforms extending Hugging Face's AnyLanguageModel approach:

**AnySpeechRecognizer:** Wraps Apple's `SpeechAnalyzer` API, lets developers swap in other recognition engines. Engines include NVIDIA's Parakeet and Alibaba's Qwen3-ASR, both running locally via Core ML. Also adds speaker diarization (who is speaking and when). Tested on macOS only (not iOS yet).

**AnyDecisionModel:** Answers yes/no, multiple-choice, and rating questions with typed results and probabilities. Reads answers from model probabilities rather than parsing generated text. Supports:
- On-device backends: MLX, Core AI, llama.cpp
- Hosted/server backends: Jev, Ollama
- Cloudflare's Clef models (trained decision head)

Demo: "Emoji Magnet" app uses yes/no questions to filter 343 emoji against a typed phrase.

**Requirements:** Swift 6.2+, macOS 26 or iOS 26+. Models download from Hugging Face Hub only when an app requests them.
