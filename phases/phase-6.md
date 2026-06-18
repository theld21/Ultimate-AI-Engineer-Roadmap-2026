## 🗺️ PHASE 6 - Large Language Models & AI Engineering

> **Goal:** This is your core domain. Master LLM fundamentals, APIs, and production patterns.

### 6.1 LLM Fundamentals

**Architecture Deep Dive**
- Transformer at scale - what changes going from 1B to 100B parameters
- Context window - how it works and limitations
- KV Cache - how it speeds up inference
- Tokenization at scale
- Positional encodings: Absolute, Relative, RoPE, ALiBi
- Flash Attention - memory-efficient attention
- Grouped Query Attention (GQA) - used in LLaMA 3
- Sliding window attention - used in Mistral

**Training LLMs**
- Pretraining - learning from internet-scale text
- Instruction tuning - following user instructions
- RLHF (Reinforcement Learning from Human Feedback)
- Constitutional AI (Anthropic's approach)
- DPO (Direct Preference Optimization) - alternative to RLHF
- Scaling laws - relationship between model size, data, compute

### 6.2 Prompt Engineering (Production-Grade)

**Prompt Anatomy**
- System prompt - role and constraints
- User prompt - the actual request
- Assistant turn - model's response history
- Few-shot examples in context

**Prompting Techniques**
- Zero-shot prompting
- One-shot and few-shot prompting
- Chain-of-Thought (CoT) - "think step by step"
- Self-consistency - generate multiple CoT paths, vote
- ReAct prompting - Reasoning + Acting (for agents)
- Tree of Thought (ToT)
- Structured output prompting - JSON, XML
- Role prompting - "You are a senior software engineer..."
- Prompt chaining - output of one prompt → input of next

**Production Prompt Engineering**
- Giving clear instruction + format + boundaries
- Always specifying what NOT to do
- Using examples and output constraints
- Prompt versioning and changelogs
- A/B testing prompts
- Prompt compression - reducing token count
- Prompt injection defense

**Tools**
- PromptLayer - tracking prompt versions
- LangSmith - LangChain observability
- OpenAI Playground
- Anthropic Console

### 6.3 Working with AI APIs

**OpenAI API**
- Chat Completions API - `messages` array
- Function calling / Tool use
- JSON mode / Structured outputs
- Streaming responses (SSE)
- Embeddings API
- Vision API (GPT-4V)
- Assistants API with file search
- Batch API for bulk processing
- Token counting with `tiktoken`
- Rate limits and quotas

**Anthropic (Claude) API**
- Messages API structure
- System prompts
- Long context (200K tokens)
- Vision support
- Tool use
- Streaming

**Google AI (Gemini) API**
- Gemini Pro / Ultra
- Multimodal inputs (text, image, video, audio)
- Real-time search grounding
- Context caching (cost reduction)

**Mistral AI API**
- Mistral 7B, 8x7B (MoE), Large
- Function calling
- JSON mode
- Open-source models via Ollama

**Meta (LLaMA) via HuggingFace / Ollama**
- LLaMA 3 models
- Running locally with Ollama
- Fine-tuning LLaMA with PEFT

**Other Key Providers**
- Cohere - enterprise embeddings, RAG
- NVIDIA NIM - GPU-optimized inference
- Groq - ultra-fast inference (LPU)
- Together AI - open-source hosting
- Replicate - model API hosting

### 6.4 API Integration Patterns

**Handling Token Limits**
- Count tokens before sending (tiktoken, anthropic tokenizer)
- Truncation strategies
- Context window management
- Summarization of old history

**Streaming APIs**
- Server-Sent Events (SSE) - streaming text chunks
- Handling partial responses
- Client-side rendering of streaming output
- Benefits: perceived latency reduction

**Rate Limiting & Retries**
- Exponential backoff with jitter
- Respect provider quotas
- Queue-based request management
- Circuit breaker pattern

**Cost Control**
- Log token usage per user/feature
- GPT-3.5 vs GPT-4 routing by task complexity
- Prompt compression (strip whitespace, summarize context)
- Caching with SHA-256 fingerprinting
- Async pipelines for non-realtime tasks

**Error Handling & Fallback**
```
try:
    response = call_gpt4(prompt)
except APIError:
    response = call_gpt35(prompt)  # cheaper fallback
except RateLimitError:
    response = get_cached_response(prompt)
except Exception:
    response = DEFAULT_MESSAGE
```

### 6.5 Secure API Integration

- **Never** expose API keys to frontend
- `.env` files locally, Secret Manager in production
- Backend proxy pattern - frontend → your API → LLM provider
- Per-user rate limiting with Redis
- API key rotation strategy
- Logging and monitoring

---

### 📦 Phase 6 Projects

**🟢 Easy: Multi-Provider AI Chatbot**
- Build a chatbot that can switch between OpenAI / Claude / Gemini
- Add streaming support with SSE
- Store conversation history in Redis
- Stack: FastAPI, OpenAI SDK, Anthropic SDK, Redis, React

**🟡 Medium: AI-Powered Resume Ranker**
- Upload a PDF resume → extract text → compare with job description
- Return match score, missing skills, feedback
- Add caching with Redis (SHA-256 fingerprinting)
- Stack: FastAPI, OpenAI, `pdf-parse`, Redis, React

**🔴 Hard: Production AI Middleware Service**
- Build a middleware that sits between your app and multiple LLM providers
- Features: intelligent routing, rate limiting, cost tracking, fallback chain, prompt logging, token counting, async batching
- Stack: FastAPI, Redis, PostgreSQL, OpenAI + Anthropic + Gemini SDKs, Docker

---

