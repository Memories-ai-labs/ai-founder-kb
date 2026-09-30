# NVIDIA Kumo Tabular Sets a New Accuracy-Efficiency Frontier for Tabular Prediction
# URL: https://huggingface.co/blog/nvidia/kumo-tabular
# Date: 2026-09-29
# Source: Hugging Face Blog

NVIDIA has released Kumo Tabular, an open foundation model for tabular data that performs classification and regression without requiring training, tuning, or feature engineering. Available on Hugging Face and GitHub, the model comes in three sizes (28M to 215M parameters) and was pretrained exclusively on artificial data.

## Key Capabilities

The model accepts labeled rows as context and predicts labels for new rows in a single forward pass. It handles both numerical and categorical columns while treating missing values without imputation.

## Architecture

Kumo Tabular uses a Transformer design incorporating column, row, and in-context attention mechanisms. The system includes cell embedding with Fourier features, row embedding through alternating attention types, and in-context learning via a final Transformer layer with Test-GQA optimization.

## Training Approach

Rather than real-world data, the model was trained on millions of artificial tables generated through Structural Causal Models. Training occurred in three stages, progressing from 1,024-row tables to contexts extending 60,000 rows.

## Performance

The model ranks first on four major benchmarks—TabArena, BeyondArena, TALENT, and ScoringBench—while executing 17× faster than comparable systems like LimiX-2 on standardized hardware.

## Limitations

The model works with numerical and categorical data only (text, images, timestamps require preprocessing), handles up to 10 classes natively, and may degrade on tables significantly different from training distributions.

## Availability

Released under the OpenMDW-1.1 license for commercial use, with code accessible via the structured-data-models library.

Authors: Jingang Qu, Valter Hudovernik, Martin Jurkovic, Cedric Lorenz, Akihiro Nitta, Dmitry Gordeev, Federico Lopez, Ramona Bendias, Gilberto Titericz Jr, Aleksandar S. Sokolovski, Isabel Hulseman, Jure Leskovec, and Matthias Fey (NVIDIA).
