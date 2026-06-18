# Agentic Resource Discovery: Let Agents Search for Tools, Skills, and Other Agents
# Source: Hugging Face Blog
# URL: https://huggingface.co/blog/agentic-resource-discovery-launch
# Date: 2026-06-17
# Publisher: Hugging Face
# Authors: Ben Burtenshaw, Shaun Smith

---

This post introduces the Agentic Resource Discovery (ARD) specification, a new open standard that enables AI agents to dynamically discover and integrate capabilities at runtime rather than requiring pre-configuration.

## The Discovery Problem

Currently, agent capabilities follow an "install-first, use-later" model where developers hardcode tool locations or users manually configure plugins. This approach doesn't scale across thousands of potential integrations. ARD shifts the paradigm by moving capability selection outside language model context windows through intent-based search.

## Core Components

**Static Manifest Format** (`ai-catalog.json`): Publishers host capabilities at a well-known URL.

**Dynamic Registry API** (`POST /search`): Provides live, ranked discovery with richer indexing signals.

## Hugging Face Implementation

Hugging Face's Discover Tool serves as a reference implementation, providing search access to thousands of Skills, ML applications, and MCP servers. It combines the Hub's semantic search infrastructure with agent-specific metadata and translates results into ARD catalog entries.

Supported media types:
- Skills (default)
- MCP server entries
- Raw Space metadata

## Access Methods

- **CLI**: `hf discover search "Fine tune a language model"`
- **REST API**: `POST https://huggingface-hf-discover.hf.space/search`
- **MCP endpoint**: Direct connection for MCP-compatible clients

## Industry Context

ARD is a collaborative specification among Microsoft, Google, GoDaddy, and Hugging Face. It operates as an open specification enabling federation across multiple registries — not a centralized marketplace.
