# New in llama.cpp: Decision Models
# URL: https://huggingface.co/blog/ggml-org/decision-models-in-llamacpp
# Date: 2026-10-02
# Source: huggingface

Authors: Xuan-Son Nguyen, ggml-org, Victor Mustar

The llama.cpp server now offers support for decision models through a `/v1/systemone` endpoint. Rather than generating text sequentially, these models "read the input once, and answer is always one of your options, with a probability attached."

## What Are Decision Models?

Decision models function differently from traditional chat models. Instead of producing text token-by-token, they score provided options in a single forward pass. This approach proves useful for request routing, content moderation, agent verification, and action selection tasks.

## Supported Models

- **Julia-1** (144M): Supports 50+ languages, 3ms response time
- **Laya** (421M): English-only, 5ms response time
- **Kev-4B** (4B): English support, 12ms response time
- **lev** (4B): English-focused, 36ms response time
- **OpenJev** (27B): Multilingual with vision capabilities, 43ms response time

## Getting Started

Users can launch a model using: `llama serve -hf ggml-org/Kev-4B-GGUF`

The API accepts three question types: choice (select from options), score (rate on a scale), and noul (yes/no). Requests include a state and questions, returning probabilities and confidence scores.

## Key Features
- Vision support for document/screenshot classification
- Multi-model server routing
- Flexible quantization options
- Batch question processing
