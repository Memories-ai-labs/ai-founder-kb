# Does Your Model Run on AWS Trainium? Look It Up
# URL: https://huggingface.co/blog/torch-neuronx-model-support
# Date: 2026-10-23
# Source: Hugging Face Blog

Author: David Corvoysier (dacorvo)

Introduces a Hugging Face Space that shows whether popular Transformers models on the Hub run unmodified on AWS Trainium, using the `torch-neuronx` package (TorchNeuron backend).

The Space has three views: a curated "Selected" list, plus "Trending" and "Downloads" views that follow Hub rankings. For each model, it reports the test result, the number of Trainium cores used, the run time, and peak device memory. It also provides a `run.py` script and install instructions, and can point to precompiled graphs in a public NEFF cache to skip compilation on the first run.

Testing currently covers only Transformers models for `text-generation` and `image-text-to-text` tasks, and only models that fit on 4 Trainium2 devices (up to 16 cores). All results come from the public `aws-neuron/torch-neuronx-model-support` dataset.
