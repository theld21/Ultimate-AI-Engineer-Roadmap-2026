## 🗺️ PHASE 5 - Natural Language Processing & Transformers

> **Goal:** Deep NLP expertise for LLM-powered products.

### 5.1 Text Preprocessing

- Tokenization - words, subwords, characters
- Lowercasing, punctuation removal, whitespace normalization
- Stopword removal - when to and when not to
- Stemming vs Lemmatization
- Sentence segmentation
- Handling special tokens: URLs, emails, hashtags
- Unicode and encoding issues (`utf-8`)

### 5.2 Classical Text Representation

- Bag of Words (BoW)
- TF-IDF - formula and intuition
- N-grams - capturing context
- One-hot encoding - and why it fails at scale
- Sparse vs dense representations

### 5.3 Word Embeddings

- Why embeddings - dense, semantic vectors
- Word2Vec - CBOW vs Skip-gram
- GloVe - global co-occurrence statistics
- FastText - subword embeddings, handles OOV
- Cosine similarity on embeddings
- Analogy tasks: `king - man + woman = queen`
- Static vs contextual embeddings

### 5.4 Subword Tokenization (Modern)

- Byte Pair Encoding (BPE) - used in GPT
- WordPiece - used in BERT
- SentencePiece - used in T5, LLaMA
- Special tokens: `[CLS]`, `[SEP]`, `[PAD]`, `[MASK]`, `<eos>`, `<bos>`
- Token IDs - how text maps to integers
- Vocabulary size tradeoffs

### 5.5 Transformer Architecture (Master This)

- Why transformers replaced RNNs - parallelism and long-range attention
- Self-attention - every token attending to every other
- Query, Key, Value (Q, K, V) - intuition and matrix formulation
- Attention score: `softmax(QKᵀ / √d_k) * V`
- Multi-head attention - attending to different aspects
- Positional encoding - injecting order
- Feed-forward sublayer
- Layer normalization and residual connections
- Encoder-only (BERT-style) - understanding tasks
- Decoder-only (GPT-style) - generation tasks
- Encoder-Decoder (T5-style) - seq2seq tasks
- Causal masking in decoders

### 5.6 Language Modeling

- `P(next token | previous tokens)`
- Autoregressive language modeling
- Masked language modeling (MLM)
- Perplexity - evaluating language models
- Temperature, Top-k, Top-p (nucleus) sampling
- Greedy vs sampling vs beam search

### 5.7 Key Pretrained Models

| Model | Type | Best For |
|---|---|---|
| BERT | Encoder-only | Classification, NER, QA |
| GPT-4 | Decoder-only | Generation, chat |
| Claude 3.5/4 | Decoder-only | Long context, safety |
| Gemini | Encoder-Decoder | Multimodal |
| T5 | Encoder-Decoder | Seq2seq tasks |
| LLaMA 3 | Decoder-only | Open-source fine-tuning |
| Mistral 7B | Decoder-only | Efficient inference |
| Qwen 2.5 | Decoder-only | Multilingual |

### 5.8 NLP Evaluation Metrics

- Accuracy, Precision, Recall, F1
- BLEU - machine translation
- ROUGE - summarization
- Perplexity - language models
- BERTScore - semantic similarity
- Human evaluation
- Exact Match (EM) - QA tasks

### 5.9 Key Python Libraries

- `NLTK` - classic NLP
- `spaCy` - production NLP: NER, parsing
- `transformers` (HuggingFace) - pretrained models
- `datasets` (HuggingFace) - loading datasets
- `sentence-transformers` - sentence embeddings
- `tiktoken` - OpenAI's tokenizer (BPE)
- `evaluate` - HuggingFace metrics

---

### 📦 Phase 5 Projects

**🟢 Easy: Named Entity Recognition (NER) Pipeline**
- Use spaCy to extract entities from news articles
- Build a simple web interface with Streamlit
- Stack: spaCy, Streamlit

**🟡 Medium: Semantic Search Engine**
- Embed 10,000 Wikipedia paragraphs with BERT
- Build a search interface that finds semantically similar passages
- Stack: HuggingFace, sentence-transformers, FAISS, Streamlit

**🔴 Hard: Fine-tune BERT for Multi-Label Classification**
- Fine-tune BERT on a multi-label text classification dataset
- Handle class imbalance, custom evaluation metrics
- Deploy as a REST API with FastAPI
- Stack: PyTorch, HuggingFace Transformers, FastAPI, Docker

---

