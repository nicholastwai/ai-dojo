# Track: RAG (Retrieval-Augmented Generation)

**Source lessons** (`ai-engineering-from-scratch`): Phase 11 lessons 04
(Embeddings & Vector Representations), 06 (RAG), 07 (Advanced RAG:
Chunking, Reranking); Phase 5 lessons 22 (Embedding Models Deep Dive) and
23 (Chunking Strategies for RAG).

## Tier 1 — Understand
- Why RAG exists: grounding responses in data the model wasn't trained on,
  and reducing hallucination on facts.
- Chunking strategies and why chunk size/overlap changes retrieval quality.
- Embeddings: what a vector actually represents, and cosine similarity at
  an intuitive level (no need for the linear algebra proof).
- Vector databases vs plain vector search — when you need one vs the other.
- Where RAG fails: multi-hop reasoning, when the answer isn't in any single
  chunk, stale indexes.

## Tier 2 — Build
- Build a minimal RAG pipeline end-to-end: ingest a real document set,
  chunk, embed, store, retrieve, and generate an answer with citations.
- Break it on purpose — try a query that needs info spanning two chunks —
  and diagnose why it fails.

## Tier 3 — Ship
- Build a RAG system over a real corpus you or someone else actually needs
  to query (candidate: internal docs, a knowledge base, product/support
  content) and have someone other than you use it to answer a real question.

## Signals you're stuck at tier 1
Can explain embeddings in an interview but have never looked at what a
badly-chunked document does to answer quality.
