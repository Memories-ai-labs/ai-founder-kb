# IBM releases SOTA Granite Time Series PatchTST-FM-r2 model with commercial-friendly license
# URL: https://huggingface.co/blog/ibm-research/ibm-releases-sota-granite-time-series
# Date: 2026-09-09
# Source: Hugging Face Blog
# Authors: Roman Vaculin, Wesley M. Gifford, Jiri Navratil, Chandra Reddy, and Ayhan Sebin (IBM Research)

IBM has released PatchTST-FM-r2, a ~385 million-parameter time series foundation model designed for zero-shot forecasting across diverse applications like demand prediction, energy loads, and sensor telemetry.

## Key Performance Metrics

- Ranks #2 among replicable, zero-shot models on GIFT-Eval leaderboard (as of September 8, 2026)
- Achieves geometric-mean CRPS of 0.467 and MASE of 0.6846
- Competitive against pretrained models despite using no benchmark training data

## Architecture Improvements

The model replaces standard transformer layers with "conformer blocks that combine multi-head self-attention with temporal convolution," enabling the model to capture both long- and short-range temporal patterns more effectively.

## Licensing & Accessibility

Dual-licensed under Apache 2.0 and OpenMDW 1.0, making it suitable for commercial applications. "The model weights, architecture, inference pipeline, and code needed to reproduce the benchmark results are all available."

## Key Capabilities

- Supports context lengths up to 8,192 steps
- Provides probabilistic forecasts through 99-quantile prediction head
- Enables missing value imputation

The model is available on Hugging Face Hub and can be implemented in just a few lines of Python code for production forecasting tasks.
