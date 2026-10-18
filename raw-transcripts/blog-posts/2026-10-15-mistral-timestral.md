# Introducing Timestral
# URL: https://mistral.ai/news/timestral/
# Date: 2026-10-15
# Source: Mistral AI Blog

---

Mistral AI's first family of time-series foundation models (TSFMs), released October 15, 2026.

## Model Sizes

Four sizes sharing one architecture and training recipe:
- **5M** — ~10 ms inference on CPU
- **28M** — beats Chronos-2 (4x larger) on GIFT-Eval and TIME
- **123M** — within 0.2% of 209M at ~3/4 the latency
- **209M** — ranks #1 on GIFT-Eval, TIME, and fev-bench

Context length: 32,768 time steps. Probabilistic multivariate forecasts with 21 quantiles.

## Key Technical Contributions

**Decoupled Horizon Forecasting (DHF):** Learned forecast tokens read the full history before generating; contrasts with contiguous patch masking in Toto 2.0 and TimesFM-3.

**Covariate-aware attention:** Information flows from covariates to targets only — prevents target future data leaking into forecasts. Supports multivariate targets, past-only covariates, and known-future covariates (including categorical).

**Synthetic-first training:** Most training data is synthetic (univariate processes with trends, seasonality, varied noise combined into multivariate series with nonlinear dependencies). Two-stage training: pre-train at 8192 context, post-train at 32,768 with real+synthetic mix.

**Loss:** Pinball loss over 21 quantiles (discrete approximation of CRPS).

## Benchmark Performance (zero-shot, single checkpoint)

| Benchmark | Metric | Timestral 209M |
|-----------|--------|----------------|
| GIFT-Eval | GMean MASE | **#1** (top 10 of 83) |
| GIFT-Eval | GMean WQL | **#1** |
| TIME | GMean MASE | **#1** (top 10 of 35) |
| TIME | GMean CRPS | **#1** |
| fev-bench | SQL skill score | **#1** (top 10 of 37) |

Beats TimesFM-3 and Falcon-2.0 with fewer parameters.

## CPU Inference Speed (8-thread server, 1-day horizon from 3 weeks of 15-min data)

- 5M: ~10 ms
- 28M: ~25 ms (5x faster than 209M)
- 123M: ~105 ms
- 209M: ~140 ms

**No GPU required at inference.**

## Availability

- **Weights:** Hugging Face + GitHub (github.com/mistralai/timestral)
- **Docs:** docs.mistral.ai/models/timestral-1-0
- **License:** Modified MIT (weights); Apache 2.0 (inference library)
- **Enterprise:** Mistral Forge — zero-shot API, fine-tuning on proprietary data, on-prem/VPC/air-gapped
- **Upcoming:** Full technical report
