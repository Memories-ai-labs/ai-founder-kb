# Google DeepMind and Singapore Government collaborate to build fine-tuned AI model for scam detection
# URL: https://deepmind.google/blog/on-device-ai-scam-detection-mddi/
# Date: 2026-10-14
# Source: Google DeepMind

Authors: JJ Geewax and Miguel de Andrés
Published: October 14, 2026
Presented at: Singapore International Cyber Week (SICW 2026)

## Summary

Google DeepMind and GovTech Singapore partnered to fine-tune a Gemma model for on-device scam detection in Singapore, processing conversations privately on-device without cloud access.

## Problem Context

- Scams account for over half of Singapore's reported crimes
- Over S$4 billion in losses since 2019
- Social engineering scams: up to 80% of losses
- Types: investment fraud, fake job offers, impersonation of public officials and banks

## Technical Approach

- Fine-tuned Google's lightweight Gemma model on local scam conversations
- Training data included impersonations of public institutions, banks, local figures, plus regional schemes
- **Two-stage pipeline:**
  1. Lightweight classifier screens incoming messages (minimal battery use)
  2. Fine-tuned Gemma model does multi-turn analysis for suspicious messages, confirms threat or dismisses false alarm
  3. User gets real-time warning to pause before sharing information or money

## Privacy Design

- Model runs on-device: neither Singapore Government nor Google can access users' conversations
- Only accesses conversations with user's consent and under each application's terms
- Fine-tuning in GovTech's managed GCP environment
- Training excluded personally identifiable information
- Stress-tested against synthetic dialogues and local corpora

## Rollout

- Phased deployment developed with the Singapore Government
- Teams plan to explore deploying similar technology in other countries

## Significance for AI Founders

On-device fine-tuned Gemma for government-partnered fraud detection is a template for sovereign AI deployments: local data, privacy-first architecture, government co-development. The two-stage classifier + LLM pipeline is a practical pattern for high-sensitivity, low-latency mobile safety applications.
