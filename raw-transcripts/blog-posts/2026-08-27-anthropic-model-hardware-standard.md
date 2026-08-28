# Previewing the Model Hardware Standard
# URL: https://www.anthropic.com/news/model-hardware-standard-research-preview
# Date: 2026-08-27
# Source: Anthropic News

## Previewing the Model Hardware Standard

Anthropic announced a research preview of the Model Hardware Standard (MHS) on August 27, 2026 — a shared specification allowing AI agents to safely operate physical devices across scientific research and manufacturing environments.

## What is MHS?

MHS provides a standardized way for AI agents to discover, communicate with, and control laboratory instruments. Rather than requiring custom integrations for each device, the system uses a universal driver approach with simple primitives like "read" and "write" commands that any hardware can understand.

## Key Features

**Standardized Communication**: MHS reduces integration work to hours or minutes compared to weeks or months previously required. The system enables devices with programmable interfaces to share data and operate in coordination through a common protocol.

**Natural Language Integration**: Researchers can describe experiments in plain language, with Claude helping orchestrate complex multi-device workflows without requiring specialized coding knowledge.

**Safety Built-In**: Device characteristics and safety limits are encoded directly into MHS drivers, preventing agents from operating equipment unsafely.

## Real-World Applications

Early testing across multiple institutions demonstrated significant improvements:

- **Genentech**: Automated protein assay procedures, with Claude independently optimizing fluid dynamics parameters
- **Carnegie Mellon**: Reduced serial dilution experiments to one-third the previous time through multi-instrument coordination
- **QuEra Computing**: AI improved laser-locking recovery from 58% to 99.3% success rates
- **HHMI Janelia**: Unified seven separate microscopy control programs into one interface

## Current Limitations

Anthropic acknowledges that Claude struggles with physical reasoning about phenomena like bubble formation and requires human guidance on context-specific physical constraints.

## Next Steps

The standard will remain in research preview before open-sourcing, with safety evaluations and best practices being developed with partners across biotech, robotics, quantum computing, and manufacturing sectors.
