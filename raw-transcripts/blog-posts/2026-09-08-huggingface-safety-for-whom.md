# Safety for Whom? Refusing the Right Subset of a Topic, Not the Whole Topic
# URL: https://huggingface.co/blog/MultiverseComputingCAI/safety-for-whom
# Date: 2026-09-08
# Source: HuggingFace Blog

Authors: Antonio Tiene, Alejo Lopez Avila, and Iker García-Ferrero (Multiverse Computing)

The article challenges conventional safety alignment approaches that treat harm at the topic level. Instead, the researchers propose "narrow-boundary safety," arguing that different deployments need different boundaries within the same topic.

Core Problem: Traditional guardrails like LlamaGuard-3 cannot distinguish between harmful and benign uses within a category. For instance, a civics tutor and public-sector assistant might need opposite behaviors on political content.

Main Contribution: The paper introduces boundary-aware training using pairs of similar prompts with different intents—one requiring refusal, one requiring response. They tested this on political persuasion, where "manipulative persuasion can cause real harm while factual political information stays legitimate."

Key Findings:
- Three weaknesses in self-generated safety data: coverage gaps (19.88% of prompts initially dropped), false refusals on benign prompts, and inadequate boundary measurement
- Solutions included escalating retry strategies and in-distribution benign data with "11,955 verified surface-dangerous benign prompts"
- Models trained purely for harm refusal often become "blunt refusal machines," sacrificing legitimate responses
- Adding boundary pairs reduced over-refusal from approximately 33% to 4% while maintaining refusal rates above 87%

Critical Insight: Safety alignment should operate at the intent/context boundary level, not the topic level — enabling deployment-specific guardrails.
