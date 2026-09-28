# YODAS v3: A 1 Million Hour Dataset for the Next Generation of Open Voice AI Research
# URL: https://huggingface.co/blog/espnet/yodasv3
# Date: 2026-09-27
# Source: Hugging Face Blog

**Authors:** William Chen and the ESPnet team

## Overview

YODAS v3 is a massively expanded multilingual speech dataset containing 1.1 million hours of audio. The creators emphasize that "training data is the true kingmaker in today's era of AI research," noting how large, diverse datasets have enabled breakthroughs in voice AI.

## Key Improvements Over v2

- **Scale**: Tripled from approximately 370,000 hours to 1.1 million hours
- **Audio Quality**: Entirely at 48kHz sampling rate; over 92% has effective frequency content equivalent to 32kHz or higher
- **Multi-channel Support**: More than 70% contains genuinely distinct multiple channels, enabling stereo and spatial audio training
- **Better Annotations**: Includes word and utterance-level timestamps, plus English translations for over half the multilingual data
- **Efficiency**: Maintains the 60TB footprint of YODAS v2 while tripling content volume

## Language Coverage

The dataset spans 100+ languages, with 34 languages containing over 1,000 hours each — sufficient for developing standalone ASR models.

## Broader Applications

Beyond automatic speech recognition, YODAS v3 enables research in:
- Speech synthesis
- Speech translation
- Audio codecs
- Speech enhancement
- Stereo/spatial audio generation

This represents a substantial expansion from earlier versions' primary ASR focus, making YODAS v3 a foundation dataset for the next generation of voice AI systems.
