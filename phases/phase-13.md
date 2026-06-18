## 🗺️ PHASE 13 - AI System Design

> **Goal:** Design AI systems at scale for real-world products and interviews.

### 13.1 AI System Design Framework

**How to approach any AI system design question:**
1. **Clarify requirements** - functional + non-functional
2. **Identify AI components** - what tasks need AI?
3. **Data flow design** - how does data move through the system?
4. **Model selection** - which LLM/model is best for each task?
5. **Scalability** - how does it handle 10x, 100x load?
6. **Cost optimization** - what's the cost per user?
7. **Reliability** - what happens when AI fails?
8. **Monitoring** - how do you know it's working?

### 13.2 Classic AI System Designs

**AI Chatbot with Memory**
```
Frontend (Chat UI) → Backend API → Session Manager (Redis)
→ Context Builder → LLM → Response → Cache → Return
Fallback: if LLM fails → cached response or template
```

**RAG Knowledge Base**
```
Documents → Ingestion Pipeline → Chunker → Embedder → Vector DB
User Query → Embed → Retrieve Top-K → Rerank → LLM → Answer
```

**Multi-LLM Recommendation System**
```
User Profile → Embedding → Vector DB Similarity
→ GPT scoring → Re-rank → Personalized Results
Feedback loop → Update embeddings
```

**PDF Q&A at Scale (10K users)**
```
Upload → Hash check → Queue → Text Extract → Chunk → Embed → Store
Query → Embed → Retrieve → Rerank → GPT → Stream Response
Cache: query-level caching with semantic similarity
```

**AI Customer Support**
```
Message → Intent classifier → Router
Low confidence → Human escalation
High confidence → RAG knowledge base → LLM response
Track: session state in Redis, conversation in PostgreSQL
```

### 13.3 Inference Placement Strategy

| Placement | Pros | Cons | Use When |
|---|---|---|---|
| Backend API | Secure, logging, easy scaling | Higher latency | Most cases |
| Client-side (browser) | Ultra-low latency, offline | Exposes model, limited | Small models |
| Edge (Cloudflare Workers) | Low latency + secure | Complex, model limits | Search autocomplete |
| Async Queue | Handle spikes, cheap | Delayed response | Long tasks |

### 13.4 Caching Strategies

**Exact Match Caching**
- SHA-256 hash of prompt → Redis key
- Best for: template-based prompts with limited variation

**Semantic Caching**
- Embed the query → find similar cached queries (cosine similarity)
- Return cached answer if similarity > threshold
- Best for: conversational apps with similar questions

**Prompt Template Caching**
- Cache at the template level, not instance level
- Best for: structured generation with variable substitution

### 13.5 Async AI Architecture

**When to use async:**
- Model latency > 2-3 seconds
- Processing expensive (PDF analysis, batch jobs)
- User doesn't need immediate response

**Async pattern:**
```
Frontend → POST /task → Task ID returned immediately
Worker → processes → updates DB
Frontend → polls GET /task/{id} or receives webhook
```

### 13.6 Cost-Aware Architecture

**Per-feature model selection:**
```
Autocomplete    → GPT-3.5 Turbo ($0.001/1K)
Summarization   → Claude Haiku  ($0.00025/1K)
Complex QA      → GPT-4o        ($0.01/1K)
Embeddings      → text-embedding-3-small ($0.00002/1K)
Classification  → Fine-tuned GPT-3.5 ($0.003/1K)
```

**Cost reduction strategies:**
- Prompt compression - remove unnecessary tokens
- Output length limits - `max_tokens` parameter
- Caching (50-70% reduction for typical apps)
- Model downgrade for free tier users
- Async batching - bundle requests
- Context window optimization

---

### 📦 Phase 13 Projects

**🟢 Easy: Design Doc for AI Feature**
- Write a 5-page design doc for an AI feature (e.g., AI writing assistant)
- Cover: architecture, data flow, model choice, cost estimate, fallback
- Get feedback from the community

**🟡 Medium: Cost Calculator Tool**
- Build a tool that estimates AI API costs given usage patterns
- Supports OpenAI, Anthropic, Gemini, Cohere pricing
- Shows cost breakdown by model, feature, user tier
- Stack: React, FastAPI

**🔴 Hard: Full AI System Design Implementation**
- Implement the complete architecture for one of the classic designs above
- Focus: production-grade, scalable, monitored, cost-aware
- Write ADRs (Architecture Decision Records) for key decisions
- Stack: Full production stack of your choice

---

