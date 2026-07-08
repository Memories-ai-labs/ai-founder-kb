# From Hugging Face to Amazon SageMaker Studio in one click

**Publisher:** Hugging Face / Amazon
**Date:** 2026-07-07
**URL:** https://huggingface.co/blog/amazon/one-click-to-sagemaker-studio
**Authors:** Hazim Qudah (with contributions from jeffboudier, alvarobartt, tomaarsen, pagezyhf, hf-dwarez)

---

This announcement describes a deep-link integration enabling developers to transition from model discovery on Hugging Face directly into Amazon SageMaker Studio workflows.

## Three main capabilities introduced

1. **Deep Links** — Action buttons ("Customize on SageMaker AI" and "Deploy on SageMaker AI") on supported models that preserve context when opening Studio
2. **Pre-configured Permissions** — New environments automatically include the AmazonSageMakerModelCustomizationCoreAccess managed policy, enabling fine-tuning, deployment, and experimentation without manual IAM setup
3. **GPU Quota Visibility** — Instance selection now displays real-time quota availability directly in the Studio UI, eliminating separate Service Quotas navigation

The integration streamlines the previously friction-filled process of discovering a model, setting up AWS infrastructure, configuring permissions, and requesting GPU quotas. Users can now accomplish this workflow in seconds.
