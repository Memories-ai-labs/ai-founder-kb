# MTEB Leaderboard: From a slow demo to feature-rich leaderboard

**Source**: HuggingFace Blog
**Date**: 2026-06-12
**URL**: https://huggingface.co/blog/Samoed/mteb-v3-leaderboard
**Authors**: Solomatin Roman (Samoed), Kenneth C. Enevoldsen, Isaac Chung

---

## Full Article

The MTEB leaderboard has undergone a significant redesign to address persistent performance issues. The original version, which started as a simple table with minimal filtering capabilities, became unreliable as the number of models and benchmarks grew, suffering from speed and uptime problems.

### Speed Improvements

The development team rebuilt the leaderboard using FastAPI and Svelte, resulting in dramatic performance gains. The new interface is described as "miles faster" than its predecessor, enabling smooth browsing even on mobile devices.

### Enhanced Exploration Features

Users can now customize benchmarks by filtering across domains, languages, modalities, and individual tasks. The interface includes hover-over tooltips for detailed model information and pinning capabilities for easy model comparisons. Separate views allow exploration of models, tasks, and their individual results.

### Transparency and Trust

The updated leaderboard integrates a HuggingFace dataset viewer, allowing users to inspect evaluation datasets and task metadata directly. Annotations indicate whether models were trained on specific tasks or evaluated zero-shot, highlighting potential evaluation concerns.

### Performance-Focused Design

Rather than exclusively ranking by peak performance, the leaderboard displays top models within size brackets and provides performance-versus-runtime analytics to encourage improvements across the broader efficiency frontier.

### Comparison Tools

Users can pin multiple models for side-by-side comparison, with an option to view detailed head-to-head analyses of selected embeddings.

### API Access

A public API is available at the backend documentation endpoint for local score retrieval and CSV downloads.

The team welcomes feature suggestions and bug reports through the project's GitHub repository.
