# Getting the Source Right, Not Just the Fact: Source-Aware Verification for MCP Agents
# URL: https://huggingface.co/blog/MultiverseComputingCAI/getting-the-source-right-not-just-the-fact-source
# Date: 2026-09-29
# Source: Hugging Face Blog

## Overview

This article introduces ProvenanceGuard, a verification system designed to address a specific failure mode in LLM agents that use the Model Context Protocol (MCP): cross-source conflation. The problem occurs when a claim is factually true somewhere in pooled evidence but attributed to the wrong source.

Authors: Antonio Tiene, Ander Alvarez Sanz, Oliver Wirjadi, Alessandro Genuardi, and others from Multiverse Computing.

## The Core Problem

Traditional faithfulness checkers like RAGAS and MiniCheck pool all retrieved evidence together, making it impossible to verify whether a claim comes from the source the agent actually names. Consider a customer support scenario: an agent states "According to the account record, this plan includes a 30-day refund window," but the refund policy actually comes from a separate policy document. Source-blind verification passes because the fact exists somewhere in the evidence pool. However, the attribution is incorrect—a critical issue in data-sensitive applications.

"A claim that is true somewhere in the evidence, but attributed to the wrong source" represents a distinct verification challenge beyond traditional hallucination detection.

## How ProvenanceGuard Works

ProvenanceGuard operates as a post-generation verification layer that preserves source identity throughout the pipeline rather than collapsing evidence into anonymous context. The system performs five sequential steps:

1. Decomposes answers into specific claims
2. Routes claims to their most relevant sources using embeddings
3. Checks whether supporting sources actually validate each claim via NLI
4. Compares the supporting source against the one the answer names or implies
5. Emits per-claim verdicts and answer-level allow/block decisions

The implementation uses local models: MiniLM for source retrieval, a DeBERTa NLI verifier, and a language model for claim decomposition. The system includes literal value checking—numbers, dates, and identifiers must appear in the source itself, not just sound plausible.

## Key Results

Testing on 281 medical agent traces with 361 claims from 40 answers showed:

- Detected 138 of 139 unsupported claims (one false negative)
- Correctly identified appropriate sources approximately 86% of the time
- Achieved 0.802 reject/block F1 score, outperforming source-blind baselines
- Successfully caught all 50 deliberately swapped source attributions in controlled testing

When distinguishing between similar sources, performance dropped to 50.3% accuracy, indicating an area requiring improvement.

## Practical Implementation

The system integrates with RARR-style repair workflows, resolving blocked answers either through source-grounded rewrites or safe fallbacks. Processing overhead is modest—approximately half a second per answer on the local configuration tested.

Real-world adoption includes NVIDIA NVFlow, which incorporated source-aware verification for its finance agent to check answers against retrieved SEC excerpts.

## Why This Matters for Multi-Tool Agents

As agents evolve from single-passage RAG to complex multi-tool MCP setups, the distinction between "any source supports this" and "the named source supports this" becomes architecturally significant.
