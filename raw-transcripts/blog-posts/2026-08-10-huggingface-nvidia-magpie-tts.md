# Build Low-Latency Multilingual Voice Agents: Open Weights & Full Deployment Control with NVIDIA Magpie TTS
# URL: https://huggingface.co/blog/nvidia/magpie-tts-multilingual-voice-agents
# Date: 2026-08-10
# source: Hugging Face Blog
# Authors: Maryam Motamedi, Mikyas Desta, Jason Li (NVIDIA)

## Summary

NVIDIA releases Magpie TTS Multilingual, a 364M-parameter open-weights text-to-speech model supporting 12 languages with ultra-low latency (32ms TTFA on B200 GPUs). New languages: Modern Standard Arabic, Korean, Brazilian Portuguese.

## Key Capabilities

- **Languages:** 12, including English, French, Hindi, Japanese, + 3 new
- **Voices:** Shared multilingual speaker representations (male + female)
- **Latency:** Time to First Audio as fast as 32ms on NVIDIA B200
- **Code-switching:** Improved for Hindi and Japanese

## Technical Architecture

Frame stacking and local transformers balance speed with audio quality. The model uses shared cross-lingual speaker embeddings, enabling natural accent and prosody across languages from a single model.

## Performance

- French character error rate reduced: 2.70% → 1.54%
- Enhanced speaker similarity metrics across all languages

## Deployment

Open-weights model for private infrastructure deployment. Part of the Nemotron Voice Agent reference architecture for complete conversational AI systems. Enterprise data privacy maintained through local deployment.

## Relevance

Open-weights TTS removes licensing barriers for startups building voice AI products. 32ms latency enables real-time agent workflows. Private deployment model addresses enterprise compliance requirements.
