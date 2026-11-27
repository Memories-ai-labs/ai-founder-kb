# Taking Trainium3 to the Track: Generating Videos with LTX-2.5
# URL: https://huggingface.co/blog/video-trainium3
# Date: 2026-11-27
# Source: Hugging Face Blog

Authors: David Corvoysier, Jingya Huang, Sayak Paul (Hugging Face)

## Summary

The post describes testing LTX-2.5, Lightricks' open model that generates video and sound together, on an AWS Trainium3 machine (trn3.48xlarge, 64 NeuronCores). Two goals: (1) how easily diffusers can generate multi-shot videos on Trainium3, (2) reach performance close to CUDA or LTX's own API.

## Key Results

- 10-second clip with sound at 2048×1024: 22-23 seconds on half the Trainium3 machine
- Slightly faster than LTX's cited API figure of 23.7 seconds for a 1080p clip
- Initial attempt: ~5 min 20 sec for 10-second clip; optimized to 22-23 seconds
- Used tensor and sequence parallelism + compiler/runtime workarounds

## Architecture

- Films defined as JSON lists of shots
- Shots chained by starting/ending on frames from other shots (keeps subjects consistent across cuts)
- Also tested LTX-2.5 as a world model on real robotics and driving footage — generates plausible continuations and alternate events

## Current Limits

- Model still gets details wrong
- Sound doesn't carry across shots
- Clips max out at 20 seconds

## Engineering Lessons

- Check device output against CPU output
- Keep traced code stable
- Generate multiple takes per shot
