# NVIDIA Nemotron 3.5 Transcribe and Granary v2: Intelligent Multilingual Transcription You Can Prompt and Adapt
# URL: https://huggingface.co/blog/nvidia/nemotron-transcribe-granary
# Date: 2026-10-28
# Source: Hugging Face Blog

Authors: Maryam Motamedi (lead), Piotr Żelasko, Kunal Dhawan, Nikolay Karpov, Nune Tadevosyan, Meline Mkrtchyan, Nithin Rao Koluguri, Francesco — all NVIDIA.

**The model:** Nemotron 3.5 Transcribe is an open-weight, promptable speech model that combines transcription, speaker attribution, translation, and audio Q&A in one checkpoint. Covers 40 languages for transcription, translates 31 to/from English, handles speaker attribution in 13. Processes recordings up to an hour long, labels up to 8 speakers.

**Benchmarks:**
- Ranks #1 among open-weight models on the Hugging Face Open ASR Leaderboard for English: 5.33% average WER
- Ties for #1 among open-weight models on Artificial Analysis at 2.8% AA-WER (~4B active parameters)
- Lowest diarization error rate on David AI's 21-language benchmark
- Lowest cpWER on VoiceArena's English full-session benchmark

**Throughput:** 100 hours of audio processed in under 3 minutes on one RTX PRO 6000 Blackwell GPU (forthcoming NVFP4 quantized version).

**Granary v2:** Open multilingual dataset covering 463,062 hours across 48 languages and 16 source corpora. Comes with a reusable curation pipeline built on NVIDIA NeMo Curator.

**Domain adaptation:** In a medical case study on Eka Care's benchmark, fine-tuning reduced held-out WER from 22.44% to 12.17% (45.8% relative reduction).

**Availability:** Hugging Face and ModelScope. Serve with vLLM or SGLang-Omni, or hosted endpoints from Baseten, DeepInfra, or Simplismart. Designed for recorded audio, not live streaming.
