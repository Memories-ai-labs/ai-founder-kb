# The Model That Didn't Exist, So You Made It Yourself
# URL: https://huggingface.co/blog/building-with-ml-intern
# Date: 2026-10-08
# Source: Hugging Face Blog

Authors: Yuvraj Sharma (ysharma) and Abubakar Abid (abidlabs)

---

Demonstrates how ML Intern — an AI agent in HuggingChat — can build six custom models in a few days for ~$103 in total compute. ML Intern plans work, asks for budget approval before spending, runs a smoke test, then trains, evaluates, and publishes each model with results.

## Models built

**Pocket prompt rewriter:** 0.8B model (plus 2B version) distilled from a 9B Qwen-Image 2.1 rewriter. Valid output 99.7% of the time; uses ~1/4 of the teacher's tokens; runs on CPU.

**Citrus disease VLM:** Fine-tuned Qwen3.5-2B for identifying citrus pests, diseases, and deficiencies. 52.8% accuracy on test photos vs. 14.9% for the base model.

**Huggy LoRA:** Style adapter for FLUX.2 klein that draws the Hugging Face mascot. Style began leaking into unrelated prompts after ~step 500.

**Viewpoint orbit LoRA:** Camera-angle adapter for Qwen-Image 2.1, trained on ~24,700 renders of scanned household objects.

**Doodle-in LoRA:** Replaces a magenta scribble in a photo with a named object. Places objects correctly 67.5% of the time.

**Agate 4-step:** Distillation of a 260M text-to-image model from 50 steps → 4, with a browser version. GenEval score: 0.536 vs. 0.563 for 50-step teacher.

## Key prompting advice

- Establish a baseline measurement before training
- Request a small smoke test first
- State budget cap upfront
- List facts already verified so the agent doesn't re-check them

## Significance

Demonstrates the emerging "AI-builds-AI" pattern: using agents to create specialized small models at low cost. Represents a shift from prompt engineering to model creation as the default tool-building primitive.
