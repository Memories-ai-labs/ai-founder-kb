# Adding MCP Tools to Reachy Mini
# URL: https://huggingface.co/blog/adding-mcp-tools-to-reachy-mini
# Date: 2026-06-03
# Source: Hugging Face Blog (Pollen Robotics)

**Author:** Alina Lozovskaya (with contributions from Victor, Jeff Boudier, Pierre Cuenq, Ari, Npaka, Sehun, and 8 others)

## Overview

The Reachy Mini conversation application now supports tools hosted on Hugging Face Spaces, accessible through the Model Context Protocol (MCP). This advancement allows users to extend the robot's capabilities without modifying the core application code.

## Key Features

**Installation is straightforward:** Users can add tools with a single command, such as `reachy-mini-conversation-app tool-spaces add pollen-robotics/reachy-mini-weather-tool`. The robot then gains new abilities like weather checking or web searching.

## Built-in vs. Remote Tools

The system maintains three categories of tools:

- **Built-in tools** (local, hardware-related): head movement, dancing, emotion playback, camera access
- **Custom local tools** (user-created, stored in `external_tools/`)
- **Remote MCP tools** (published on Hugging Face Spaces): stateless capabilities like search and weather

As stated in the article, "It's a good fit for stateless capabilities like search, weather, and lookups: anything you want to iterate on without touching the app itself."

## Profile-Based Control

Profiles regulate tool availability through a `tools.txt` file. Users can create focused profiles combining different tool sets—for example, one profile includes emotional expression tools alongside web search functionality.

## Current Capabilities and Limitations

The system successfully supports:
- Installation from public, MCP-compatible Gradio Spaces
- Multiple concurrent Spaces
- Per-profile tool enablement
- Backend-agnostic registration

However, private Spaces, non-Gradio implementations, and arbitrary MCP URLs remain unsupported.

## Publishing Tools

Developers can share custom tools by creating public Gradio Spaces with standard MCP endpoints. The article recommends tagging tools with `reachy-mini-tool` and `mcp` for discoverability.
