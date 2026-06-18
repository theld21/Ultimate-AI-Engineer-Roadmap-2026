## 🗺️ PHASE 4 - Deep Learning

> **Goal:** Understand neural networks deeply enough to work with transformers.

### 4.1 Neural Network Fundamentals

- Neuron, Perceptron, MLP
- Activation functions: Sigmoid, Tanh, ReLU, GELU, SwiGLU
- Forward pass - how information flows
- Backpropagation - how gradients flow backward
- Weight initialization strategies
- Vanishing / exploding gradient problem

### 4.2 Training Techniques

- Batch normalization - stabilizing training
- Layer normalization - used in transformers
- Dropout - stochastic regularization
- Residual connections (skip connections) - used in every modern model
- Gradient clipping

### 4.3 Convolutional Neural Networks (CNN)

- Convolution operation - feature detection
- Pooling layers - spatial downsampling
- CNN architectures: LeNet, AlexNet, VGG, ResNet
- Transfer learning with CNNs
- Applications: image classification, object detection

### 4.4 Recurrent Neural Networks (RNN)

- RNN - processing sequences one step at a time
- Hidden state - memory across time steps
- Vanishing gradient in RNNs
- LSTM - cell state, forget/input/output gates
- GRU - simpler LSTM alternative
- Bidirectional RNNs
- Seq2Seq: encoder + decoder
- Beam search decoding

### 4.5 Attention Mechanism (Pre-Transformer)

- Attention as "soft" alignment
- Additive vs multiplicative attention
- Bahdanau attention for seq2seq
- Why attention solved the bottleneck problem

### 4.6 PyTorch (Master This)

- Tensors - creation, operations, GPU
- `torch.nn.Module` - building models
- `torch.optim` - Adam, SGD, etc.
- Custom datasets with `torch.utils.data.Dataset`
- DataLoader - batching and shuffling
- Training loop: forward → loss → backward → step
- `model.eval()` vs `model.train()`
- Saving/loading: `torch.save()`, `torch.load()`
- Moving to GPU: `.to(device)`
- Gradient computation: `.requires_grad`, `torch.no_grad()`
- Custom loss functions
- Learning rate schedulers

### 4.7 Transfer Learning

- What is pretraining and why it matters
- Fine-tuning vs feature extraction
- Freezing layers
- ImageNet moment for NLP
- Using HuggingFace pretrained models

---

### 📦 Phase 4 Projects

**🟢 Easy: Image Classifier with Transfer Learning**
- Fine-tune ResNet-18 on a custom image dataset (5 categories)
- Track train/val accuracy, plot loss curves
- Stack: PyTorch, torchvision, Matplotlib

**🟡 Medium: Sentiment Analysis with LSTM vs BERT**
- Build LSTM from scratch, then use pretrained BERT
- Compare performance on movie reviews dataset
- Stack: PyTorch, HuggingFace Transformers

**🔴 Hard: Build a Mini GPT from Scratch**
- Implement the full transformer architecture: attention, multi-head attention, positional encoding, feed-forward, residual connections
- Train on a small text corpus (Shakespeare/wiki)
- Stack: PyTorch, NumPy (follow Andrej Karpathy's nanoGPT style)

---

