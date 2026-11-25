# An Indic Voice Agent with CUGA
# URL: https://huggingface.co/blog/ibm-research/an-indic-voice-agent-with-cuga
# Date: 2026-11-25
# source: Hugging Face Blog (IBM Research)

Authors: Vrunda Gadesha, Cyril Shaji, Jobit Treesa Varughese, Nivetha Suruliraj, Anu Sugunan, Anupama Murthi, Jaydeep Sen, Amith Singhee

## Summary

IBM Research demonstrates a voice-based Farm Assistant for Indian farmers. A farmer asks a spoken question in their regional language; the agent transcribes it, searches a 154-page English agricultural handbook, and answers in 2–4 spoken sentences in the same language using only the handbook. Source pages are shown so answers can be checked; off-topic questions are redirected to farming.

## Architecture

- **Core:** CUGA (IBM Research's open-source agent harness) — text-in, text-out. Handles model wiring, tools, state, and guardrails. Works as an embedded SDK; can switch between watsonx and OpenAI.
- **Speech wrapper:** STT + TTS wrap CUGA. Options: Sarvam AI cloud APIs (browser-side) or open-source (SraVaani for STT, Svara for TTS) on own server.
- **Knowledge engine:** Parses, chunks, embeds, and searches handbook locally. Each question gets a fresh conversation thread.

## Key challenge: Cross-lingual retrieval

CUGA's default English-only embedding model failed on Hindi and Tamil questions, retrieving wrong passages without raising errors. Fix: multilingual embedding model (`intfloat/multilingual-e5-large`) — one English document serves every language. Advice: test retrieval with a non-English question before tuning prompts.

## Engineering practices

- Prompts and formatter strip markdown and citation tags so output sounds natural when spoken.
- Cheap input checks catch obvious off-topic questions; if one gets through, the model replies with a marker and the app substitutes a polite redirect — avoids extra LLM call.
- Answers grounded in retrieved passages only.
- With Sarvam option, API keys stay in browser and never reach the server.

## Broader applicability

Same approach applies to scheme documents, health advisories, or legal guides. Providers can be changed for cloud or on-premises (data sovereignty) needs. Related to IBM Bharat Core, an AI stack for running Indic workloads on local infrastructure.

## Resources

- Live demo in CUGA Apps on Hugging Face Spaces
- Step-by-step tutorial, CUGA website, GitHub repos (Apache 2.0)
