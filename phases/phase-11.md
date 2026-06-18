## 🗺️ PHASE 11 - Generative AI (Beyond Text)

### 11.1 Variational Autoencoders (VAEs)

- Encoder → latent space → decoder
- KL divergence loss + reconstruction loss
- Reparameterization trick
- Applications: image generation, anomaly detection

### 11.2 Generative Adversarial Networks (GANs)

- Generator vs Discriminator
- Minimax game
- Mode collapse - the main challenge
- Conditional GANs (cGAN)
- StyleGAN, DCGAN
- Applications: image synthesis, style transfer

### 11.3 Diffusion Models

- Forward process - adding noise to data
- Reverse process - learning to denoise
- DDPM (Denoising Diffusion Probabilistic Models)
- Score matching
- DDIM - faster sampling
- Classifier-free guidance
- Stable Diffusion architecture
- ControlNet - conditional generation

### 11.4 Text-to-Image APIs

- DALL-E 3 API - OpenAI
- Stable Diffusion via Replicate / HuggingFace
- Midjourney (no API, UI-based)
- Ideogram, Flux - newer models
- Prompt engineering for image generation
- Negative prompts

### 11.5 Multimodal AI

- Vision-Language Models (VLMs)
- GPT-4V / GPT-4o - text + image input
- Claude 3 Vision
- Gemini (text + image + video + audio)
- LLaVA - open-source VLM
- CLIP - connecting text and images
- Applications: image captioning, visual QA, document understanding

### 11.6 Audio AI

- OpenAI Whisper - speech-to-text
- TTS: OpenAI TTS, ElevenLabs, Coqui
- Music generation: Suno, Udio
- Voice cloning
- Real-time speech processing

### 11.7 Video AI

- Sora (OpenAI) - text-to-video
- Runway ML, Pika Labs
- Video understanding with Gemini
- Frame-by-frame analysis

---

### 📦 Phase 11 Projects

**🟢 Easy: Image + Text Multi-Modal QA**
- Build an app: upload an image, ask a question about it
- Use GPT-4V or Claude Vision
- Stack: FastAPI, OpenAI Vision API, React

**🟡 Medium: AI Image Generation Pipeline**
- Build a text-to-image app with style controls
- Add image-to-image transformation
- Add safety filtering with moderation API
- Stack: DALL-E 3 API, Stable Diffusion (Replicate), FastAPI, React

**🔴 Hard: Voice AI Assistant (Full Pipeline)**
- Voice input → Whisper STT → LLM processing → TTS output
- Features: streaming audio, wake word detection, multi-language support
- Stack: OpenAI Whisper, GPT-4, ElevenLabs TTS, FastAPI, React Native

---

