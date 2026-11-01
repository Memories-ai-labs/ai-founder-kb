# MonsterHouse: Building a Haunted House with NVIDIA Nemotron Open Models
# URL: https://huggingface.co/blog/nvidia/nemotron-halloween
# Date: 2026-10-30
# Source: Hugging Face Blog (NVIDIA)
# Authors: Rick Grandy, Maryam Motamedi (NVIDIA)

NVIDIA engineers built MonsterHouse, an interactive Halloween projection that turns a garage door into a grumpy, pirate-themed haunted house. Visitors speak to the house, which answers in a cantankerous voice and warms up when they use polite language ("please," "thank you"). The project demonstrates NVIDIA's Nemotron open model stack running on a single workstation with dual Blackwell GPUs.

**System architecture:**
- Nemotron Speech ASR: transcribes visitor speech
- Nemotron 3.5 Bolt E4B 4-bit: generates replies (with a LoRA adapter trained on thousands of reviewed conversations for personality)
- Magpie TTS Zeroshot: speaks replies using short voice samples across seven moods
- Audio2Face-3D: drives the wooden character's mouth in Unreal Engine 5
- Nemotron 3 Nano Omni: describes visitors' costumes
- YOLO + ByteTrack: counts and tracks people

The conversation flow brushes visitors off initially and rewards persistence and politeness. State tracking (whether a visitor has been polite) is handled by the application, not the model. A bank of prepared text and cached audio kept median latency to ~1.7s for live generation and ~0.7s for cached responses. A control desk lets the operator switch modes, adjust moods, and monitor the system.

The project is not open-sourced but provides a step-by-step path for similar builds using the NVIDIA Voice Agent, Bolt E4B, Magpie TTS, Audio2Face-3D, and Nemotron Omni.

**Relevance:** Practical end-to-end demonstration of NVIDIA's open Nemotron model stack for real-time, multi-modal interactive character AI on consumer hardware.
