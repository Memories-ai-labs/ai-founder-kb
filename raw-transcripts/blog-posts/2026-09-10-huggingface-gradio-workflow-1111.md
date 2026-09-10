# Rebuilding AUTOMATIC1111 with Gradio Workflow
# URL: https://huggingface.co/blog/gradio-workflow-1111
# Date: 2026-09-10
# Source: Hugging Face Blog
# Authors: Yuvraj Sharma and Abubakar Abid

The Hugging Face team rebuilt most of AUTOMATIC1111's stable-diffusion-webui feature set as a single workflow canvas using Gradio. The resulting application, called Workflow1111, comprises eleven interconnected media pipelines built from 73 nodes.

## Key Components

The workflow integrates multiple AI capabilities on one canvas:

- **Text-to-image generation** with style presets and metadata storage
- **Hi-resolution enhancement** using FLUX.1-Kontext for upscaling and refinement
- **Image editing** through the same model with different prompts
- **LLM prompt enhancement** via Qwen3-4B that expands rough descriptions into detailed tags
- **Image interrogation** using Qwen2.5-VL and ViT classifiers to reverse-engineer prompts
- **Object detection** with DETR to automatically generate inpainting masks
- **Prompt matrix grids** that generate multiple image variants in parallel
- **Upscaling and background removal** leveraging both local processing and external Spaces
- **ControlNet-style preprocessors** (Canny, line art, etc.) implemented as NumPy functions
- **Metadata preservation** through PNG info storage and retrieval
- **Image-to-video animation** with Wan 2.2

## Technical Architecture

The system uses four operator types: `fn` (Python functions), `model` (inference calls), `space` (other Gradio applications), and `dataset` (Hub datasets). Approximately two-thirds of the canvas remains functional without internet connectivity since many nodes run locally.

## API and Integration

"Every output node on the canvas becomes a REST endpoint, with no routes written by hand." The application exposes nine endpoints and functions as a Model Context Protocol server, enabling AI assistants to access its capabilities.

## Comparison with ComfyUI

While both platforms use node-graph architecture, Gradio Workflow emphasizes browser accessibility, automatic API generation, and straightforward Python function integration for custom nodes.
