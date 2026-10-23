# OlmoEarth v1.3: State-of-the-art embeddings for the whole planet
# URL: https://huggingface.co/blog/allenai/olmoearth-v1-3
# Date: 2026-10-22
# Source: Hugging Face Blog (Allen AI / Ai2)

Author: Kyle Wiggers (Ai2Comms)

A satellite embedding model from Allen Institute for AI (Ai2). Reads a year of radar (Sentinel-1) and multispectral (Sentinel-2 and Landsat) time series and outputs a 128-dimensional vector for each 10-meter pixel.

**Released assets:**
- OlmoEarth v1.3 Base model
- Precomputed global annual embeddings (10m, 64 and 128 dimensions) on Source Cooperative
- Browser-based OlmoEarth Embeddings Explorer
- Technical report

**Performance:** Across 27 evaluations, 128-dimensional embeddings scored highest on 20, and 64-dimensional led on 18. Comparisons were against AlphaEarth Foundations and Tessera v2.

**Efficiency:** Training took ~53% of the compute of v1.2 and 18% of v1. Final pretraining run estimated at ~$2,720 of rented H100 time.

**Case study:** Embedding change maps of La Pampa, Peru show shifts in illegal gold mining from 2017–2020 to 2020–2025, following a 2019 government crackdown.

Everything published under the OlmoEarth Artifact License (open). Introduced PLANTEUR, a tropical crop-type benchmark.
