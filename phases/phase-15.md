## 🗺️ PHASE 15 - Quantization, Optimization & Efficiency

> **Goal:** Run models efficiently at scale.

### 15.1 Model Quantization

- What is quantization - reducing precision of weights
- FP32 → FP16 → BF16 → INT8 → INT4
- Post-Training Quantization (PTQ)
- Quantization-Aware Training (QAT)
- GPTQ - accurate quantization method for LLMs
- AWQ (Activation-aware Weight Quantization)
- GGUF - format for llama.cpp (local inference)
- Using `bitsandbytes` library for 4-bit/8-bit

### 15.2 Inference Optimization

- KV Cache - avoiding recomputation
- Continuous batching - dynamic batching of requests (vLLM's approach)
- Speculative decoding - use small draft model to speed up large model
- Flash Attention v2 - memory-efficient attention
- Tensor parallelism - splitting model across GPUs
- Pipeline parallelism - pipelining layers across GPUs

### 15.3 Small Language Models (SLMs)

- Phi-3 / Phi-4 (Microsoft) - powerful small models
- Gemma 2 2B (Google) - efficient small model
- Mistral 7B - best open-source small model
- Qwen 2.5 1.5B, 3B - multilingual SLMs
- SmolLM - tiny models for edge
- When SLMs beat LLMs (specific tasks, fine-tuned)
- On-device AI with SLMs

### 15.4 Knowledge Distillation

- Teacher-student training
- Soft labels from teacher
- Intermediate layer distillation
- DistilBERT - distilled BERT
- TinyLlama - distilled LLaMA
- Applications: deploy 7B capability in 1B parameters

### 15.5 Model Serving Efficiency

- **vLLM** - PagedAttention, continuous batching, 24x throughput
- **TGI (Text Generation Inference)** - HuggingFace production server
- **Ollama** - local model serving
- **llama.cpp** - CPU inference, GGUF format
- **ONNX Runtime** - cross-platform inference
- **TensorRT-LLM** - NVIDIA optimized

---

### 📦 Phase 15 Projects

**🟢 Easy: Local LLM Setup**
- Set up Ollama with multiple models (LLaMA 3, Mistral, Gemma)
- Build a simple chat interface connecting to local models
- Benchmark: latency, memory usage per model

**🟡 Medium: Model Quantization Comparison**
- Take LLaMA 3 8B, quantize to 8-bit and 4-bit (GPTQ, AWQ)
- Benchmark: perplexity, speed, memory, task performance
- Stack: bitsandbytes, GPTQ, HuggingFace

**🔴 Hard: High-Throughput Inference Server (CodeLLM)**
- Deploy vLLM with multiple models
- Implement request batching, model switching, load balancing
- Benchmark against naive implementation
- Stack: vLLM, Docker, Kubernetes, Prometheus, Grafana

---

