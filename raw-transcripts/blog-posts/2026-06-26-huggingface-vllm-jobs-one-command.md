# Run a vLLM Server on HF Jobs in One Command

Title: Run a vLLM Server on HF Jobs in One Command
Author: Quentin Gallouédec (Hugging Face)
URL: https://huggingface.co/blog/vllm-jobs
Date: 2026-06-26
Source: Hugging Face Blog (Official)

---

## Summary

This guide demonstrates how to deploy a vLLM server on Hugging Face infrastructure using a single command. Users can spin up a private, OpenAI-compatible LLM endpoint on Hugging Face infrastructure with a single `hf jobs run` command.

## Key Features

- **Pay-per-second billing** with no server provisioning required
- **OpenAI API compatibility** for easy integration with existing tooling
- **Token-based authentication** for secure access (private by default)
- **Support for models** ranging from small (4B parameters) to very large (122B+)

## Practical Applications

The article covers:
- Querying via curl or Python's OpenAI client
- Creating a chat interface with Gradio
- SSH access for debugging
- Integration with AI coding agents

## When to Use

The post distinguishes HF Jobs as ideal for "experiments, one-off evals, batch generation" versus Inference Endpoints, which suit production services with scale-to-zero capabilities.

## Security Model

Endpoint security requires HF tokens for access, making it private by default rather than public-facing.
