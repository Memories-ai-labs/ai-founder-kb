# NeoMME: An Efficient Multimodal-Native and Multilingual Encoder
# URL: https://huggingface.co/blog/Hcompany/neomme
# Date: 2026-09-03
# Source: Hugging Face Blog
# Authors: Tony Wu, Aurélien Lac, and H Company team

## Summary

NeoMME is a family of efficient multimodal encoders (260M and 800M parameters) designed for visual document retrieval and representation learning. Unlike typical visual language models that combine separate pretrained vision and text components, "a single bidirectional Transformer processes both text tokens and raw image patches" trained from scratch.

## Key Technical Points

**Architecture:** Single bidirectional Transformer processes both text tokens and raw image patches trained from scratch — unified multimodal representation vs. combined pretrained components.

**Cost-Effective Deployment:** The 260M model outperforms larger competitors while offering "2× ColModernVBERT's throughput" on document encoding — directly reducing infrastructure costs for production systems.

**Document Processing:** NeoMME-Retriever enables visual RAG (retrieval-augmented generation) by preserving layout, tables, and charts that OCR-based approaches miss — critical for enterprise document analysis.

**Compression Technology:** The compression techniques reduce storage "from roughly 1.5 MB to 6 kB per page (255× smaller) while retaining more than 95% of baseline nDCG@10," making large-scale deployments feasible.

**Open Availability:** All model checkpoints under the Apache 2.0 license with Hugging Face Transformers integration.

**Multilingual Support:** Native multilingual capabilities (131k-token vocabulary) serves global enterprises better than single-language alternatives.

## Enterprise Relevance

High relevance for founders building document intelligence products: cost-effective visual RAG, large-scale document retrieval, and multilingual support with open licensing.
