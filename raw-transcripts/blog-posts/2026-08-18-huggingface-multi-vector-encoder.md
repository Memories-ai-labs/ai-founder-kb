# Multi-Vector (Late Interaction) Embedding Models with Sentence Transformers
# URL: https://huggingface.co/blog/multi-vector-encoder
# Date: 2026-08-18
# Source: HuggingFace Blog

Multi-Vector (Late Interaction) Embedding Models with Sentence Transformers

Published August 18, 2026

Authors: Tom Aarsen (tomaarsen), Antoine Chaffin (NohTow / lightonai), Raphael Sourty (raphaelsty / lightonai)

Sentence Transformers is a Python library for using and training embedding and reranker models for applications like retrieval augmented generation, semantic search, and more. With the v6.0 update, it gains a fourth model type: MultiVectorEncoder, for ColBERT-style late interaction retrieval. Any PyLate checkpoint and any Stanford-NLP ColBERT checkpoint loads straight into it, and colpali-engine models for visual document retrieval can be used too, through the same familiar API you already use for dense, sparse, and reranker models.

Where a regular embedding model compresses a whole text into one vector, a multi-vector model keeps one vector per token and scores query against document with the MaxSim operator. That preserves token-level matching information that a single vector has to average away, which usually means stronger retrieval at the cost of a bigger index. It's also the state of the art for visual document retrieval, where a text query is matched against page images directly, with no OCR step in between.

## What are Multi-Vector Models?

A dense embedding model reads a text and returns a single fixed-size vector. Everything the model noticed has to fit in those 384, 768, or 1024 numbers, and similarity is one dot product between two such summaries. This works remarkably well, but the compression is lossy in a specific way: a rare entity, an exact identifier, or one crucial clause in a long passage all have to compete for room in the same vector.

A multi-vector model (also called a late-interaction or ColBERT-style model) skips that compression. It runs the same transformer, but instead of pooling the token embeddings into one vector, it projects each token embedding down to a small dimension (classically 128) and keeps all of them. A 9-token document becomes a 9x128 matrix, not a 1x128 vector. The interaction between query and document is then deferred until scoring time ("late interaction").

## The MaxSim Operator

Scoring uses MaxSim: for each query token, take its highest similarity against any document token, then sum those maxima across the query.

MaxSim(Q, D) = Σ(Qi ∈ Q) max(Dj ∈ D) Qi · Dj

Because the token embeddings are L2-normalized, each dot product is a cosine similarity in [-1, 1], so the whole sum lands within [-num_query_tokens, num_query_tokens]. The alignment doesn't have to be lexical, since the token embeddings are contextualized.

## What You Gain, and What It Costs

You gain retrieval quality, particularly on:
- Queries where one specific piece of a document is what makes it relevant
- Multi-requirement queries where each requirement gets to find its own evidence
- Out-of-domain data where a dense model's compression was tuned for a different distribution

The cost is index size. One vector per token instead of one vector per document is a lot more vectors. Encoding 4,874 Natural Questions passages with lightonai/LateOn produced 608,414 token vectors (average 124.8 per passage):

| Representation | Vectors | Dimensions | float32 size |
|---|---|---|---|
| Dense, all-MiniLM-L6-v2 | 4,874 | 384 | 7.5 MB |
| Dense, gte-modernbert-base | 4,874 | 768 | 15.0 MB |
| Multi-vector, LateOn | 608,414 | 128 | 311.5 MB |

That's about 42x the storage of MiniLM, though PLAID compression reduces this to ~92 MB.

## Usage

```python
from sentence_transformers import SentenceTransformer

# Load a ColBERT-style model
model = SentenceTransformer("lightonai/LateOn")

# Encode queries and documents
queries = ["What is the capital of France?", "When was Python released?"]
documents = ["Paris is the capital of France.", "Python was first released in 1991."]

query_embeddings = model.encode(queries, convert_to_tensor=True)
doc_embeddings = model.encode(documents, convert_to_tensor=True)

# Score with MaxSim
scores = model.similarity(query_embeddings, doc_embeddings)
```

The v6.0 update brings ColBERT-style late interaction retrieval to the same familiar Sentence Transformers API previously used for dense, sparse, and reranker models. PyLate capabilities now live natively in Sentence Transformers itself.

## Supported Models
- lightonai/LateOn
- lightonai/mLateOn (multilingual)
- Stanford-NLP ColBERT checkpoints
- PyLate-compatible checkpoints
- colpali-engine models (for visual document retrieval)

## Key Applications
- Retrieval Augmented Generation (RAG)
- Semantic search over long documents
- Visual document retrieval (page images, no OCR needed)
- Audio and video retrieval
- Multi-hop retrieval requiring exact token matching
