# Build specialized multimodal models with LFM3
# URL: https://huggingface.co/blog/LiquidAI/lfm3
# Date: 2026-10-27
# Source: Hugging Face Blog

Team Article from LiquidAI. Contributors: Leonie Monigatti, Jimmy T.H. Smith, Anthony Maltsev, Maxime Labonne, and others.

LFM3 is Liquid AI's new generation of Liquid Foundation Models, all ~2B parameters. Covers text, vision, audio, omni, and decision models built on one shared backbone.

**Key improvements from LFM2:**
- **Efficiency:** LFM3-1.7B beats LFM2.5-2.6B with ~35% fewer parameters
- **Coverage:** Six models built from LFM3-1.7B-Base, including first omni model and video input for vision model
- **Edge deployment:** Text model fits in ~1 GB at 4-bit precision, 256K-token context window
- **Specialization:** Each model can be fine-tuned on a single GPU

**Architecture:** Mixes gated short convolutions with sliding-window and global attention layers. Also adds head-wise gated attention, partial RoPE, and sandwich normalization. Faster than LFM2 at long context lengths.

**Models:**
- **LFM3-1.7B:** Text, for local agents and tool calling
- **LFM3-VL-2B:** Text, image, and video input, text output
- **LFM3-Audio-2B:** Speech-in and speech-out, 18 languages
- **LFM3-Omni-2B:** Text, image, video, and audio input, text or speech output
- **d1-2B and d1-omni-2B:** Return calibrated probabilities for structured decisions

All models open-weight on Hugging Face, in the LFM3 collection. Includes fine-tuning notebooks (SFT, DPO, GRPO, CPT) and a robotics example built on LFM3-VL-2B.
