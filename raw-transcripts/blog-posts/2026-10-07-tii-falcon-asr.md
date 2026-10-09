# Introducing Falcon ASR
# URL: https://huggingface.co/blog/tiiuae/falcon-asr
# Date: 2026-10-07
# Source: Hugging Face Blog / Technology Innovation Institute (TII)

Authors: Abdul Muneer, Rishabh Saraf, Ramesh Gundluru, Shamsa Hamad, Lepauloux, and Hakim Hacid (TII, Abu Dhabi)

---

Falcon-ASR is a 1.6B-parameter speech recognition model from TII in Abu Dhabi. It focuses on Arabic (especially Emirati dialect) and also handles English, French, Spanish, and Portuguese with the same weights. Supports word-level timestamps.

## Performance

- **Arabic (6 test sets, Open Universal Arabic ASR Leaderboard):** 20.92% WER avg vs. best published 23.17%
- **Emirati speech (TII internal):** 22.73% WER, 10.19% CER — lowest among compared systems
- **English (7 test sets):** 5.74% WER avg

## Training details

- Trained on Emirati, MSA, other Arabic dialects, and English
- Data augmentation: noise, overlapping speech, music, reverberation, telephony effects, speed and pitch changes
- Builds on the team's earlier Falcon3-Audio work

## Availability

- Hugging Face demo Space live
- API access and native apps planned
- Apache 2.0 or similar open license
