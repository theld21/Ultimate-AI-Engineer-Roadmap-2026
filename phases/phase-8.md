## 🗺️ PHASE 8 - RAG & Vector Databases

> **Goal:** Build retrieval systems that give LLMs access to your private knowledge.

### 8.1 Why RAG Exists

- LLMs have knowledge cutoffs
- LLMs can't access private/proprietary data
- LLMs hallucinate when they don't know
- RAG = Embedding-based search + Prompt-based generation
- RAG vs Fine-tuning - when to use which

### 8.2 Embeddings Deep Dive

- What are embeddings - dense, semantic vector representations
- Embedding models: `text-embedding-3-small`, `text-embedding-3-large` (OpenAI)
- `all-MiniLM-L6-v2`, `bge-large` (open source, HuggingFace)
- `embed-english-v3` (Cohere) - tuned for RAG
- Embedding dimensions - tradeoff between quality and storage
- Batch embedding for efficiency
- Embedding similarity: cosine, dot product, Euclidean

### 8.3 Chunking Strategies

- Fixed-size chunking - simple but naive
- Sentence-based chunking - respects natural boundaries
- Recursive character text splitting - LangChain default
- Semantic chunking - split on topic change
- Document-based chunking - by headers, sections
- Chunk size vs overlap tradeoff
- Chunk metadata - source, page, section

### 8.4 Vector Databases

| DB | Type | Best For |
|---|---|---|
| **FAISS** | Local | Prototyping, research |
| **Chroma** | Local / Cloud | Early production |
| **Pinecone** | Managed | Production scale |
| **Weaviate** | Self-hosted | Metadata filtering |
| **Qdrant** | Self-hosted | High performance |
| **LanceDB** | Embedded | Serverless apps |
| **pgvector** | PostgreSQL ext | Existing Postgres users |
| **MongoDB Atlas** | Managed | Full-stack apps |
| **Supabase** | Managed | Postgres + vectors |

**Vector DB Operations**
- Indexing - storing embeddings with metadata
- Similarity search - finding nearest neighbors
- Filtered search - metadata + vector similarity
- Hybrid search - keyword + vector (BM25 + embeddings)
- Namespace/collection isolation - multi-tenant
- HNSW index - Hierarchical Navigable Small World (algorithm behind most vector DBs)

### 8.5 RAG Pipeline Implementation

**Basic RAG**
```
Document → Chunk → Embed → Store in Vector DB
                                    ↓
User Query → Embed → Retrieve Top-K Chunks
                                    ↓
            Chunks + Query → LLM → Answer
```

**Advanced RAG Techniques**
- **Hypothetical Document Embeddings (HyDE)** - generate hypothetical answer, embed it for retrieval
- **Query expansion** - generate multiple query variants
- **Reranking** - use a cross-encoder to rerank retrieved chunks (Cohere Rerank, BGE Reranker)
- **Multi-query retrieval** - decompose complex question into sub-queries
- **Self-querying** - LLM generates structured filter from natural language
- **Contextual compression** - compress retrieved context before sending to LLM
- **Parent document retriever** - retrieve small chunks, return parent document
- **Multi-vector retriever** - multiple embeddings per document (summary + full text)

**RAG Evaluation**
- Faithfulness - is the answer grounded in retrieved context?
- Answer relevance - does the answer address the question?
- Context precision - are the retrieved chunks relevant?
- Context recall - did we retrieve all necessary information?
- Tools: RAGAs framework, LangSmith, TRULENS

### 8.6 Production RAG Considerations

- Incremental indexing - adding new documents without reindexing
- Document versioning - handling document updates
- Multi-tenant isolation - per-user, per-org vector spaces
- Caching - cache embeddings, cache query results
- Monitoring - retrieval quality, latency, hit rates
- Fallback - "I don't know" when context is insufficient

---

### 📦 Phase 8 Projects

**🟢 Easy: Chat with Your PDF**
- Upload a PDF, chunk and embed it, ask questions
- Stack: LangChain, OpenAI, Chroma, Streamlit

**🟡 Medium: Multi-Document Knowledge Base**
- Ingest multiple documents (PDF, DOCX, TXT, web pages)
- Hybrid search: BM25 + vector similarity
- Source attribution in answers
- Stack: LlamaIndex, Qdrant, Cohere Rerank, FastAPI, React

**🔴 Hard: Enterprise RAG System (RoadmapAI Context)**
- Multi-tenant RAG with namespace isolation
- Incremental document ingestion pipeline
- Advanced retrieval: HyDE + reranking + contextual compression
- RAG evaluation dashboard with RAGAs
- Production deployment with Redis caching and monitoring
- Stack: LangChain, Pinecone, Cohere, FastAPI, Redis, PostgreSQL, Grafana, Docker

---

