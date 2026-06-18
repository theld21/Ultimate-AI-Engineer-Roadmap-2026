## 🗺️ PHASE 12 - MLOps, LLMOps & Production Systems

> **Goal:** Ship AI to production reliably, cheaply, and scalably.

### 12.1 Data Management & Versioning

- DVC (Data Version Control) - versioning datasets and models
- Data validation - Great Expectations, Pandera
- Data lineage - tracking data origins
- Feature stores - Feast, Tecton
- Data pipelines - Airflow, Prefect, Luigi

### 12.2 Experiment Tracking

- Weights & Biases (W&B) - industry standard
- MLflow - open source alternative
- What to track: hyperparameters, metrics, artifacts, code version
- Comparing runs and reporting

### 12.3 Model Development & Training Infrastructure

- GPU cloud: AWS (SageMaker, EC2), GCP (Vertex AI), Azure ML
- Distributed training: PyTorch DDP, DeepSpeed, FSDP
- Mixed precision training (FP16, BF16)
- Model checkpointing
- Training monitoring and alerting

### 12.4 Model Evaluation & Testing

**Offline Evaluation**
- Task-specific benchmarks
- Human evaluation with guidelines
- LLM-as-judge (GPT-4 evaluating other models)
- Red teaming - adversarial testing

**Online Evaluation**
- A/B testing models in production
- Shadow deployment - run new model in parallel
- Canary releases - gradual traffic shifting
- User feedback collection (thumbs up/down)

### 12.5 Model Deployment & Serving

**API Serving**
- FastAPI - the standard for ML APIs
- Flask - simpler, less performant
- gRPC - for high-throughput internal services
- BentoML - ML-specific serving framework
- Ray Serve - distributed serving

**Model Optimization for Serving**
- Quantization - INT8, INT4 (reduce model size)
- Pruning - removing unnecessary weights
- Knowledge distillation - smaller student model
- ONNX - framework-agnostic model format
- TensorRT - NVIDIA optimized inference

**Inference Backends**
- Ollama - local model serving
- vLLM - high-throughput LLM serving (PagedAttention)
- TGI (Text Generation Inference) - HuggingFace
- LiteLLM - unified API for all providers
- NVIDIA NIM - production-grade inference

### 12.6 Containerization & Orchestration

- Docker - containerize everything
- `Dockerfile` for ML services
- Multi-stage builds for smaller images
- Docker Compose - local multi-service development
- Kubernetes (K8s) - production orchestration
- Helm charts - K8s app packaging
- Horizontal Pod Autoscaler (HPA) - scale based on load
- GPU scheduling in K8s

### 12.7 Cloud Deployment

**AWS**
- EC2 + SageMaker for ML
- Lambda for lightweight AI functions
- ECS / EKS for containers
- S3 for model/data storage
- CloudWatch for monitoring

**GCP**
- Vertex AI - full ML platform
- Cloud Run - serverless containers
- GKE - managed Kubernetes
- BigQuery for ML data

**Azure**
- Azure ML
- Azure OpenAI Service - enterprise OpenAI
- AKS - managed Kubernetes

### 12.8 Monitoring & Logging

**LLM-Specific Monitoring**
- Token usage per user/feature (cost)
- Latency (p50, p95, p99)
- Error rates by provider
- Prompt quality monitoring
- Response quality scores
- Hallucination detection
- Drift detection - model behavior changes

**Tools**
- **LangSmith** - LangChain observability
- **Helicone** - OpenAI proxy with analytics
- **Langfuse** - open-source LLM observability
- **Prometheus + Grafana** - general metrics
- **Datadog** - full-stack monitoring
- **Sentry** - error tracking

### 12.9 CI/CD for AI

- GitHub Actions / GitLab CI for AI pipelines
- Automated testing for ML (pytest + model tests)
- Model validation before deployment
- Prompt regression testing
- Automated model evaluation in CI
- Feature flags for AI features
- Blue-green deployments

### 12.10 LLM Security & Safety

**Prompt Injection Defense**
- System/user role separation
- Input sanitization - blocking override phrases
- Output validation
- Logging suspicious prompts
- File injection scanning (PDFs, DOCX)

**Content Moderation**
- OpenAI Moderation API
- Pre-screening user input
- Post-screening model output
- Category-based blocking: hate, self-harm, NSFW
- Custom classifiers for domain-specific content

**Data Privacy**
- PII detection and masking before sending to APIs
- Data residency requirements (EU, US, India)
- On-premise deployment for sensitive data
- Audit logs for compliance

---

### 📦 Phase 12 Projects

**🟢 Easy: Dockerize an AI API**
- Containerize your FastAPI + OpenAI app
- Add health checks, proper logging, env var management
- Deploy to a cloud provider (Railway, Render, or AWS)
- Stack: Docker, FastAPI, GitHub Actions

**🟡 Medium: LLMOps Monitoring Dashboard**
- Instrument your AI API with Langfuse or Helicone
- Track: token usage, latency, error rates, cost per user
- Build alert rules for anomalies
- Stack: FastAPI, Langfuse/Helicone, Grafana, PostgreSQL

**🔴 Hard: Production AI Platform on Kubernetes**
- Multi-service AI platform: API gateway, router service, LLM proxy, monitoring
- Kubernetes deployment with HPA for auto-scaling
- CI/CD pipeline with GitHub Actions
- Full observability: Prometheus, Grafana, Langfuse
- Stack: FastAPI, Redis, PostgreSQL, Docker, Kubernetes, Helm, GitHub Actions, Prometheus, Grafana

---

