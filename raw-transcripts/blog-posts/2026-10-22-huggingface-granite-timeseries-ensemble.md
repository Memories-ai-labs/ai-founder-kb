# Ensemble Forecasting with IBM Granite Time-Series Models
# URL: https://huggingface.co/blog/ibm-research/granite-timeseries-ensemble-r1
# Date: 2026-10-22
# Source: Hugging Face Blog (IBM Research)

## Authors
Fearghal O'Donncha, Chandramouli Kamanchi, Guruprasad Ranjini, Wesley M. Gifford, Natalia Martinez Gil, Bradley Eck, Pankaj Dayama, Roman Vaculin, Ayhan Sebin (IBM Research)

## Summary

Introduces Granite Timeseries Ensemble — a default forecasting recipe combining four pre-trained IBM Granite time-series models (PatchTST-FM-r1, PatchTST-FM-r2, FlowState-r1.1, TTM-r3). Returns median and quantile forecasts without retraining or fitted ensemble weights.

## Two Aggregation Methods

1. **Probabilistic Ensemble (recommended default):** Equal weighting; pools quantile forecasts from all four members.
2. **IQR Ensemble:** Weights members by forecast spread (narrower intervals get more influence). Caution: narrower intervals ≠ better calibration.

## Performance
- On GIFT-Eval: both recipes beat all four individual members on aggregate MASE and average MASE rank
- PatchTST-FM-r2 retains the best aggregate CRPS/MWQL score

## Limitations
- Channels forecast independently
- Higher inference cost vs. single member
- Calibration not guaranteed under distribution shift
- Recommended to backtest on representative data

## Significance
IBM continuing to invest heavily in open-source time-series foundation models on Hugging Face. The ensemble approach makes model selection less critical for practitioners.
