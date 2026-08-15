# OlmoEarth Embeddings: Custom Embedding Exports from OlmoEarth Studio for Downstream Analysis
# URL: https://huggingface.co/blog/allenai/olmoearth-embeddings
# Date: 2026-08-12
# Source: Hugging Face Blog (Allen Institute for AI)

## Overview

Allen Institute for AI introduced custom embedding exports from OlmoEarth Studio, enabling researchers and developers to generate compact numerical representations of satellite imagery for downstream analysis using open-source foundation models.

## Key Features

**Configurable Parameters:**
- Area of interest (custom polygons)
- Time span (1-12 monthly periods)
- Three encoder variants: Nano (128-dim), Tiny (192-dim), or Base (768-dim)
- Spatial resolution options: 10m, 20m, 40m, or 80m per pixel
- Data sources: Sentinel-2 L2A, Sentinel-1 RTC, or both

Outputs delivered as Cloud-Optimized GeoTIFFs with embeddings stored as signed 8-bit integers.

## Practical Applications

**Similarity Search:** Identifying pixels with comparable landscape characteristics through cosine similarity — "find more like this" without labels.

**Few-Shot Segmentation:** Training land-cover classifiers from minimal labeled data — F1 = 0.84 with only 60 labeled pixels for mangrove detection.

**Change Detection:** Comparing temporal embeddings to identify surface changes — demonstrated through wildfire burn scar identification.

**Unsupervised Exploration:** PCA dimensionality reduction to visualize embedding structure and discover natural landscape patterns.

## Technical Notes

Simple operations (linear regression, PCA) over frozen embeddings yield effective results — no fine-tuning required for many applications. Fine-tuning support available for higher-performance use cases.

## Resources

- Tech report, GitHub tutorials, Colab notebook available
- Fully open-source models and weights
