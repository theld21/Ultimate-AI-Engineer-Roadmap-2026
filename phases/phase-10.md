## 🗺️ PHASE 10 - Fine-Tuning & Model Customization

> **Goal:** Customize models for your specific domain and use case.

### 10.1 When to Fine-Tune

**Fine-tune when:**
- You need consistent output format that prompt engineering can't achieve
- You have domain-specific knowledge (medical, legal, code)
- You need to reduce prompt length (bake instructions into model)
- You need better performance on a specific task

**Don't fine-tune when:**
- RAG can solve the problem cheaper
- You don't have enough quality data (< 50-100 examples is usually not enough)
- The task is easily solved with prompt engineering
- You need latest knowledge (fine-tuning doesn't update knowledge)

### 10.2 Full Fine-Tuning

- Understanding the fine-tuning pipeline
- Data preparation - instruction format: `{"prompt": "...", "completion": "..."}`
- OpenAI fine-tuning API (GPT-3.5, GPT-4o-mini)
- HuggingFace `Trainer` API
- Training data quality > quantity
- Validation set - monitoring overfitting
- Hyperparameters: learning rate, epochs, batch size

### 10.3 Parameter-Efficient Fine-Tuning (PEFT)

**LoRA (Low-Rank Adaptation)**
- Intuition - inject small trainable matrices into attention layers
- Rank (r) - tradeoff between efficiency and capacity
- Alpha (scaling factor)
- Which layers to apply LoRA to
- Merging LoRA weights into base model

**QLoRA (Quantized LoRA)**
- 4-bit quantization of base model
- LoRA on top of quantized model
- Fine-tune 70B models on consumer GPU
- NF4 quantization (Normal Float 4)

**Other PEFT Methods**
- Prefix Tuning - trainable prefix tokens
- Prompt Tuning - soft prompts
- IA3 - inject trainable vectors into attention and FFN

### 10.4 Fine-Tuning Tools

- **HuggingFace PEFT library** - standard for LoRA/QLoRA
- **TRL (Transformer Reinforcement Learning)** - SFT, RLHF, DPO
- **Unsloth** - 2x faster fine-tuning, less memory
- **Axolotl** - production fine-tuning framework
- **LLaMA-Factory** - easy fine-tuning UI
- **Weights & Biases** - experiment tracking
- **MLflow** - model versioning

### 10.5 Dataset Preparation

- Instruction-following format (Alpaca format)
- Chat format (ShareGPT format)
- DPO format: chosen vs rejected responses
- Data cleaning and deduplication
- Data augmentation techniques
- Quality filtering - removing low-quality examples
- Data mixing strategies

### 10.6 Evaluation After Fine-Tuning

- Task-specific metrics (BLEU, ROUGE, F1, accuracy)
- Benchmark suites: MMLU, HumanEval, MT-Bench
- Human evaluation
- LLM-as-judge evaluation
- Regression testing - ensure you didn't degrade on other tasks

---

### 📦 Phase 10 Projects

**🟢 Easy: Fine-tune GPT-3.5 on Custom Q&A**
- Prepare 100 high-quality Q&A pairs in your domain
- Fine-tune via OpenAI API
- Compare base vs fine-tuned model performance
- Stack: OpenAI Fine-tuning API, Python

**🟡 Medium: LoRA Fine-tune LLaMA on Code**
- Fine-tune LLaMA 3 8B with LoRA for code generation in a specific language/framework
- Use HuggingFace PEFT + TRL
- Evaluate on HumanEval
- Stack: HuggingFace PEFT, TRL, Unsloth, W&B

**🔴 Hard: Full RLHF Pipeline (CodeLLM Context)**
- Collect preference data (chosen vs rejected code completions)
- Train reward model
- Apply DPO to fine-tune base model
- Evaluate on custom benchmark
- Stack: TRL, HuggingFace, PyTorch, Axolotl, W&B, Docker

---

