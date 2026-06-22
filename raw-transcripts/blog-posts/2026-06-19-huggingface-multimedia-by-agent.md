# No Photoshop, No Blender: Multimedia by Agent
# URL: https://huggingface.co/blog/mishig/multimedia-by-agent
# Date: 2026-06-19
# source: HuggingFace Blog
# Author: Mishig Davaadorj

---

## Overview

Community article demonstrating how AI agents can replace entire creative software stacks (Photoshop, Blender) by chaining together model API endpoints through Hugging Face Spaces.

## The Core Argument

"The creative stack collapses from install and learn N applications down to describe what you want" — by using callable API endpoints instead of traditional software suites.

## The agents.md Contract

Every Gradio Space exposes documentation that specifies how an agent can interact with it:
- API schemas
- Endpoints
- Authentication requirements

This standardized interface enables agents to discover and compose tools without hardcoded integrations.

## The Two-Step Pipeline (3D Figurine Studio)

1. **FLUX.2-dev**: Converts reference photos + prompts into identity-preserving figurine portraits
2. **TRELLIS.2**: Transforms single images into textured 3D meshes in `.glb` format

Unlike previous examples in the series, end-users can run the same pipeline using their own authentication tokens and quotas — making it self-serve rather than centralized.

## Key Implications

- **Creative software commoditization**: Multi-app creative workflows (design + 3D modeling + rendering) become single-prompt agent tasks
- **Open-weight models + documented interfaces**: The combination enables "describe what you want" multimedia creation at zero license cost
- **Hugging Face Spaces as agent tool registry**: Each Space becomes a callable tool in a broader agent orchestration layer

## Significance for Founders

This post illustrates the **creative software disruption thesis** in practice: the next generation of creative tools won't be new GUI applications but agent orchestration layers that compose existing model capabilities. Founders building creative tools need to compete against this abstraction layer, not just against other GUI apps like Canva or Figma.
