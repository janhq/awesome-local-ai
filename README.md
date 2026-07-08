# Awesome Local AI [![Awesome](https://awesome.re/badge.svg)](https://github.com/sindresorhus/awesome)

> A curated list of tools, frameworks, models, and resources for running AI **locally** — on your own machine, your own server, your own rack. No cloud required. No data leaving your network.

Local AI is having a moment. Consumer GPUs are getting faster, models are getting smaller, runtimes are getting better, and the legal/compliance pressure (GDPR, the EU AI Act, HIPAA, internal-data policies) is making "cloud-only" a non-starter for a growing slice of work. This list focuses on the practical question: **what do you actually run, today, on hardware you own?**

Every entry is hand-checked. We prefer projects that are:

- **Open source** (or have a usable free local tier).
- **Actively maintained** (commits within the last ~6 months).
- **Documented well enough** to install in under an hour.
- **Honest about hardware requirements** — the README tells you what you'll need.

> If a project no longer meets the bar, [open an issue](../../issues/new?template=report-broken.yml) and it'll be reviewed.

---

## Contents

- [Local LLM Runtimes](#local-llm-runtimes)
- [Desktop Apps & Web UIs](#desktop-apps--web-uis)
- [Code Assistants](#code-assistants)
- [RAG & Knowledge](#rag--knowledge)
- [Agents](#agents)
- [Image Generation](#image-generation)
- [Speech: TTS & STT](#speech-tts--stt)
- [Vision, OCR & Document AI](#vision-ocr--document-ai)
- [Embeddings](#embeddings)
- [Vector Databases (Local-Friendly)](#vector-databases-local-friendly)
- [Mobile & On-Device](#mobile--on-device)
- [Inference Optimization & Quantization](#inference-optimization--quantization)
- [Models & Model Hubs](#models--model-hubs)
- [Benchmarks & Evaluation](#benchmarks--evaluation)
- [Self-Hosting Stacks](#self-hosting-stacks)
- [Hardware Guide](#hardware-guide)
- [Communities](#communities)
- [Newsletters, Blogs & Podcasts](#newsletters-blogs--podcasts)
- [Tutorials & Learning](#tutorials--learning)

---

## Local LLM Runtimes

The engines that actually load weights and produce tokens. Pick one as the base of your stack.

- [llama.cpp](https://github.com/ggerganov/llama.cpp) - The foundational C/C++ inference engine. GGUF format, runs on CPU, CUDA, Metal, Vulkan, ROCm. Powers most of the projects below.
- [Ollama](https://ollama.com) - One-command model management on top of llama.cpp. The easiest "from zero to chatting" experience on macOS, Linux, and Windows.
- [LM Studio](https://lmstudio.ai) - Polished desktop app, GUI model browser, standard chat-completion API compatible local server. Free for personal use.
- [Jan](https://jan.ai) - Fully open-source desktop alternative to LM Studio. Cross-platform, plugin system, MIT-licensed.
- [vLLM](https://github.com/vllm-project/vllm) - High-throughput, production-grade inference server. PagedAttention, tensor parallelism, standard chat-completion API compatible API. Pick this when you're serving more than one user.
- [SGLang](https://github.com/sgl-project/sglang) - Newer high-throughput serving runtime focused on structured generation and complex prompting. Often faster than vLLM on supported models.
- [text-generation-webui](https://github.com/oobabooga/text-generation-webui) - Gradio web UI with broad backend support (Transformers, llama.cpp, ExLlama). The Swiss Army knife.
- [koboldcpp](https://github.com/LostRuins/koboldcpp) - Single-binary llama.cpp distribution with a friendly UI, popular for story writing and roleplay.
- [mlx-lm](https://github.com/ml-explore/mlx-examples/tree/main/llms) - Apple's MLX framework for native Apple Silicon inference. Best raw throughput on M-series Macs.
- [MLC LLM](https://github.com/mlc-ai/mlc-llm) - Compile LLMs to run on phones, browsers, and embedded devices via TVM.
- [LocalAI](https://github.com/mudler/LocalAI) - Drop-in replacement for the standard chat-completion API. Supports LLMs, image gen, TTS, STT, embeddings in one binary.
- [exllamav2](https://github.com/turboderp-org/exllamav2) - Fast inference of quantized models on consumer NVIDIA GPUs. Excellent for long-context use cases.
- [mistral.rs](https://github.com/EricLBuehler/mistral.rs) - Rust-based inference engine, focus on speed and a clean API. CUDA, Metal, CPU.
- [llamafile](https://github.com/Mozilla-Ocho/llamafile) - Distribute a model as a single executable that runs everywhere. Magic for sharing.
- [Nitro](https://github.com/janhq/cortex.cpp) (now Cortex) - Embeddable inference engine from the Jan team.
- [candle](https://github.com/huggingface/candle) - Hugging Face's minimalist ML framework in Rust. Good for embedding inference into Rust apps.
- [TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM) - NVIDIA's high-performance inference library. Squeeze maximum tokens/sec out of a datacenter GPU.

---

## Desktop Apps & Web UIs

Front-ends that let humans actually use the runtimes above.

- [Open WebUI](https://github.com/open-webui/open-webui) - The de facto self-hosted chat UI. Multi-user, RAG built in, plugin system, runs on Docker in one command.
- [LibreChat](https://github.com/danny-avila/LibreChat) - Polished multi-user chat UI. Bring-your-own keys for cloud models, but pairs cleanly with local backends.
- [AnythingLLM](https://github.com/Mintplex-Labs/anything-llm) - All-in-one desktop app: chat + workspaces + RAG over your documents. Available as desktop binary or self-hosted server.
- [GPT4All](https://gpt4all.io) - Friendly desktop chat client with a built-in model library. Solid first install for non-technical users.
- [Msty](https://msty.app) - Slick cross-platform chat app supporting local and cloud models side-by-side. Closed source but free tier is generous.
- [h2oGPT](https://github.com/h2oai/h2ogpt) - Enterprise-flavored local LLM + RAG platform from H2O.ai.
- [Lobe Chat](https://github.com/lobehub/lobe-chat) - Pretty chat UI with plugin system; can be pointed at any standard chat-completion API compatible local server.
- [Big-AGI](https://github.com/enricoros/big-AGI) - Feature-dense web UI: branching conversations, beam search, persona library.
- [chatbox](https://github.com/chatboxai/chatbox) - Cross-platform desktop client; speaks to local APIs.
- [Page Assist](https://github.com/n4ze3m/page-assist) - Browser extension that lets local LLMs see your current page. Surprisingly useful.
- [Enchanted](https://github.com/AugustDev/enchanted) - Native macOS / iOS app for talking to Ollama instances.
- [Sanctum](https://sanctum.ai) - macOS-native chat app, privacy-first framing.
- [Off Grid AI Desktop](https://github.com/off-grid-ai/off-grid-ai-desktop) - Local-first macOS desktop app: LLM chat, image generation, whisper dictation, and RAG over your own data, all on-device via llama.cpp. AGPL-3.0.

---

## Code Assistants

Editor integrations that keep your codebase on your machine.

- [Continue](https://continue.dev) - Open-source autocomplete + chat for VS Code and JetBrains. Pluggable backend (Ollama, LM Studio, vLLM, llama.cpp, anything standard chat-completion API compatible).
- [Tabby](https://github.com/TabbyML/tabby) - Self-hosted code completion server (Rust). Team-scale alternative to cloud autocomplete services.
- [twinny](https://github.com/twinnydotdev/twinny) - VS Code extension specifically built for Ollama-backed autocomplete and chat.
- [Aider](https://github.com/Aider-AI/aider) - Terminal-based pair programmer. Works fully offline with any local standard chat-completion API compatible endpoint.
- [Cline](https://github.com/cline/cline) - Agentic coding extension for VS Code; supports local model endpoints.
- [llama-coder](https://github.com/ex3ndr/llama-coder) - VS Code extension; Ollama-only, focused on completions.
- [Privy](https://github.com/srikanth235/privy) - Open-source autocomplete + chat focused on privacy.
- [Refact.ai](https://github.com/smallcloudai/refact) - Open-source self-hosted code assistant (chat + completions + agents).
- [CodeGPT](https://codegpt.co) - Pluggable VS Code / JetBrains extension; supports local providers.

---

## RAG & Knowledge

Index your own files, query them with a local model.

- [PrivateGPT](https://github.com/zylon-ai/private-gpt) - Pioneering "chat with your docs, 100% local" project. Battle-tested foundation.
- [kotaemon](https://github.com/Cinnamon/kotaemon) - Open-source RAG UI focused on document Q&A; good citation/visualization story.
- [Khoj](https://github.com/khoj-ai/khoj) - Self-hostable AI second brain. Index notes, docs, email; queryable from Obsidian, Emacs, web.
- [DocsGPT](https://github.com/arc53/DocsGPT) - RAG specifically for project documentation. Embeddable widget for your docs site.
- [Onyx](https://github.com/onyx-dot-app/onyx) (formerly Danswer) - Open-source enterprise search and chat across SaaS connectors. Self-hostable.
- [Verba](https://github.com/weaviate/Verba) - Weaviate's reference RAG app. Good code to learn from.
- [RAGFlow](https://github.com/infiniflow/ragflow) - Document-aware RAG with strong table/PDF parsing.
- [Cognita](https://github.com/truefoundry/cognita) - Modular RAG framework with UI.
- [LlamaIndex](https://github.com/run-llama/llama_index) - Library for building RAG and structured-data agents. Local-first if you wire it up that way.
- [Haystack](https://github.com/deepset-ai/haystack) - Production-oriented framework for search, RAG, and agents.

---

## Agents

Multi-step, tool-using systems that you can run end-to-end without cloud APIs.

- [Letta](https://github.com/letta-ai/letta) (formerly MemGPT) - Stateful agents with long-term memory. Local-model friendly.
- [Open Interpreter](https://github.com/OpenInterpreter/open-interpreter) - Run code on your machine via natural language. Local-model mode is well-supported.
- [CrewAI](https://github.com/crewAIInc/crewAI) - Multi-agent orchestration framework. Pair with local standard chat-completion API compatible endpoint.
- [AutoGen](https://github.com/microsoft/autogen) - Microsoft's conversation-driven agent framework. Local backends supported.
- [LangGraph](https://github.com/langchain-ai/langgraph) - Graph-based agent runtime from the LangChain team.
- [Pydantic AI](https://github.com/pydantic/pydantic-ai) - Type-safe agent framework; works with any local standard chat-completion API compatible server.
- [smolagents](https://github.com/huggingface/smolagents) - Hugging Face's minimalist agent library; code-first agents.
- [AgentKit](https://github.com/BCG-X-Official/agentkit) - Full-stack starter for production-grade agents.

---

## Image Generation

- [AUTOMATIC1111 stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui) - The classic, feature-dense Stable Diffusion web UI.
- [ComfyUI](https://github.com/comfyanonymous/ComfyUI) - Node-graph UI for diffusion pipelines. The serious-user choice; everything new lands here first.
- [Fooocus](https://github.com/lllyasviel/Fooocus) - Friction-free SDXL image generation. No prompt-engineering tax.
- [InvokeAI](https://github.com/invoke-ai/InvokeAI) - Polished UI, good for professional workflows, strong canvas/inpaint UX.
- [SD.Next](https://github.com/vladmandic/sdnext) - Maintained fork of A1111 with broader backend and model support.
- [Stable Diffusion WebUI Forge](https://github.com/lllyasviel/stable-diffusion-webui-forge) - Performance-focused A1111 fork by the ControlNet author.
- [DiffusionBee](https://diffusionbee.com) - Native macOS app. One-click install.
- [Diffusers](https://github.com/huggingface/diffusers) - Hugging Face library; build your own pipelines in Python.
- [SwarmUI](https://github.com/mcmonkeyprojects/SwarmUI) - Modular UI built on ComfyUI as the backend.
- [krita-ai-diffusion](https://github.com/Acly/krita-ai-diffusion) - Diffusion inside Krita. Pro illustrators love it.

---

## Speech: TTS & STT

### Speech-to-Text

- [whisper.cpp](https://github.com/ggerganov/whisper.cpp) - Pure C/C++ port of Whisper. Runs anywhere, even Raspberry Pi.
- [faster-whisper](https://github.com/SYSTRAN/faster-whisper) - CTranslate2 reimplementation, ~4× faster than reference Whisper.
- [WhisperX](https://github.com/m-bain/whisperX) - Whisper + word-level timestamps + speaker diarization.
- [whisper-timestamped](https://github.com/linto-ai/whisper-timestamped) - Word-accurate timestamps without retraining.
- [Vosk](https://alphacephei.com/vosk/) - Offline speech recognition in many languages. Tiny models, great for embedded.
- [Moonshine](https://github.com/usefulsensors/moonshine) - Fast STT for resource-constrained devices.

### Text-to-Speech

- [Piper](https://github.com/rhasspy/piper) - Fast neural TTS, runs on Raspberry Pi. The default choice for offline voice assistants.
- [Coqui TTS](https://github.com/coqui-ai/TTS) - Battle-tested TTS toolkit. Project is archived but the code still works.
- [F5-TTS](https://github.com/SWivid/F5-TTS) - Excellent voice-cloning TTS with short reference clips.
- [Kokoro](https://huggingface.co/hexgrad/Kokoro-82M) - 82M-parameter TTS model with surprisingly good quality.
- [StyleTTS 2](https://github.com/yl4579/StyleTTS2) - High-quality, style-controllable TTS.
- [OpenVoice](https://github.com/myshell-ai/OpenVoice) - Voice cloning with cross-lingual support.
- [XTTS-v2](https://huggingface.co/coqui/XTTS-v2) - Multi-lingual zero-shot voice cloning.
- [MeloTTS](https://github.com/myshell-ai/MeloTTS) - Multi-language TTS optimized for CPU inference.
- [Bark](https://github.com/suno-ai/bark) - Generative audio model (speech + nonverbal sounds + music).

---

## Vision, OCR & Document AI

- [Florence-2](https://huggingface.co/microsoft/Florence-2-large) - Microsoft's multi-task vision model. Captioning, detection, OCR, grounding — all in one small model.
- [Moondream](https://github.com/vikhyat/moondream) - Tiny (sub-2B) vision-language model. Runs on a phone.
- [LLaVA](https://github.com/haotian-liu/LLaVA) - Open vision-language assistant.
- [BakLLaVA](https://github.com/SkunkworksAI/BakLLaVA) - LLaVA on Mistral.
- [surya](https://github.com/VikParuchuri/surya) - Multilingual OCR, layout analysis, reading order detection.
- [docling](https://github.com/docling-project/docling) - IBM's document parsing toolkit (PDF, DOCX, etc. → structured JSON).
- [Marker](https://github.com/VikParuchuri/marker) - PDF → clean Markdown. Tables, math, images preserved.
- [DocTR](https://github.com/mindee/doctr) - OCR with pretrained models in PyTorch and TensorFlow.
- [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) - Mature, multilingual OCR toolkit.

---

## Embeddings

Local-first embedding models for retrieval, semantic search, and clustering.

- [nomic-embed-text](https://huggingface.co/nomic-ai/nomic-embed-text-v1.5) - Open-weights long-context (8K) embedding model. Strong default.
- [bge-large / bge-m3](https://huggingface.co/BAAI/bge-m3) - BAAI's general-purpose embedding family; multilingual variants.
- [mxbai-embed-large](https://huggingface.co/mixedbread-ai/mxbai-embed-large-v1) - Strong English embeddings, runs in Ollama directly.
- [Stella](https://huggingface.co/dunzhang/stella_en_1.5B_v5) - Compact, high-MTEB-rank embedding family.
- [Arctic Embed](https://huggingface.co/Snowflake/snowflake-arctic-embed-l) - Snowflake's retrieval-tuned models.
- [jina-embeddings-v3](https://huggingface.co/jinaai/jina-embeddings-v3) - Multilingual, multi-task. Open weights, commercial-friendly.

---

## Vector Databases (Local-Friendly)

Storage you can run on your own box.

- [Qdrant](https://github.com/qdrant/qdrant) - Rust-based vector DB. Single binary, excellent docs, hybrid search.
- [Chroma](https://github.com/chroma-core/chroma) - The default "just works" embeddings DB for prototyping.
- [LanceDB](https://github.com/lancedb/lancedb) - Embedded vector DB built on Lance columnar format. Lives in your app process.
- [Milvus](https://github.com/milvus-io/milvus) - Scalable, production-grade. Has a lightweight `milvus-lite` mode.
- [Weaviate](https://github.com/weaviate/weaviate) - Mature, hybrid lexical + vector. Docker-friendly self-host.
- [pgvector](https://github.com/pgvector/pgvector) - Vector extension for PostgreSQL. The boring, reliable choice.
- [sqlite-vec](https://github.com/asg017/sqlite-vec) - Vector search inside SQLite. Tiny, embedded, no server.
- [Vespa](https://github.com/vespa-engine/vespa) - Engineering-heavy but extremely capable hybrid search engine.
- [txtai](https://github.com/neuml/txtai) - All-in-one semantic search + workflows library; embedded vector store included.

---

## Mobile & On-Device

LLMs on your phone, on your watch, on a Pi.

- [PocketPal](https://github.com/a-ghorbani/pocketpal-ai) - Cross-platform mobile chat app. Bring your own GGUFs.
- [LLMFarm](https://github.com/guinmoon/LLMFarm) - iOS llama.cpp wrapper.
- [Maid](https://github.com/Mobile-Artificial-Intelligence/maid) - Cross-platform Flutter app.
- [Layla](https://www.layla-network.ai) - Privacy-focused Android assistant.
- [Apple Foundation Models](https://developer.apple.com/documentation/foundationmodels) - Apple's on-device model API (iOS 18.2+). Free, no API key, no data leaves the device.
- [picoLLM](https://github.com/Picovoice/picollm) - Mobile-first compressed-LLM inference SDK from Picovoice.

---

## Inference Optimization & Quantization

Smaller, faster, less memory — without throwing away quality.

- [AutoAWQ](https://github.com/casper-hansen/AutoAWQ) - Activation-aware weight quantization.
- [AutoGPTQ](https://github.com/AutoGPTQ/AutoGPTQ) - Classic GPTQ quantization, well-supported.
- [bitsandbytes](https://github.com/bitsandbytes-foundation/bitsandbytes) - On-the-fly 4-bit / 8-bit loading for HF models.
- [hqq](https://github.com/mobiusml/hqq) - Half-Quadratic Quantization. Fast PTQ, no calibration data.
- [Optimum](https://github.com/huggingface/optimum) - Hugging Face's optimization layer (ONNX, TensorRT, OpenVINO).
- [onnxruntime-genai](https://github.com/microsoft/onnxruntime-genai) - Microsoft's ONNX-based generative inference runtime.
- [IPEX-LLM](https://github.com/intel/ipex-llm) - Intel's LLM acceleration for CPU and Arc GPUs.

---

## Models & Model Hubs

Where to actually get the weights.

- [Hugging Face Hub](https://huggingface.co/models) - The de facto model registry. Filter by `gguf`, `mlx`, `awq`, `gptq` for ready-to-run quantizations.
- [Ollama Model Library](https://ollama.com/library) - Curated, pre-packaged models with one-command pulls.
- [TheBloke (archived)](https://huggingface.co/TheBloke) - Historical archive of community quantizations. Still useful for older models.
- [bartowski](https://huggingface.co/bartowski) - Current go-to community quantizer for newer models.
- [unsloth](https://huggingface.co/unsloth) - Pre-quantized, fine-tune-ready model variants.
- [mlx-community](https://huggingface.co/mlx-community) - Apple Silicon-optimized model conversions.
- [LMSYS Chat-1M](https://huggingface.co/datasets/lmsys/lmsys-chat-1m) - Real conversation dataset for evaluation.

---

## Benchmarks & Evaluation

How to know if your local setup is actually good.

- [Open LLM Leaderboard](https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard) - Reference HF leaderboard. Synthetic but useful baseline.
- [LiveBench](https://livebench.ai) - Contamination-resistant, refreshed monthly.
- [LMSYS Chatbot Arena](https://lmarena.ai) - Human-vote pairwise leaderboard. The closest thing to "how good does it feel".
- [lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) - The standard library for running benchmarks locally.
- [Open Medical-LLM Leaderboard](https://huggingface.co/spaces/openlifescienceai/open_medical_llm_leaderboard) - Domain-specific evaluation.
- [BigCodeBench](https://github.com/bigcode-project/bigcodebench) - Coding benchmark for code-trained models.
- [MTEB](https://huggingface.co/spaces/mteb/leaderboard) - Massive Text Embedding Benchmark. Pick your embedding model from here.

---

## Self-Hosting Stacks

Docker / Kubernetes / one-shot scripts that wire several of the above together.

- [Open WebUI + Ollama Compose](https://docs.openwebui.com/getting-started/quick-start/) - Reference one-command stack.
- [Harbor](https://github.com/av/harbor) - Containerized "all the local AI tools" launcher with profiles for hundreds of services.
- [Cog](https://github.com/replicate/cog) - Containers for ML, built by Replicate. Good for packaging your own models.
- [Helmet](https://github.com/yusing/godoxy) - Reverse-proxy + auto-cert wrapper popular for self-hosting LLM stacks.
- [Pinokio](https://pinokio.computer/) - Browser-based installer for hundreds of local AI apps. Great for quick experiments.
- [GPUStack](https://github.com/gpustack/gpustack) - Multi-node GPU cluster manager for self-hosted inference at small-team scale.
- [KubeAI](https://github.com/substratusai/kubeai) - Kubernetes operator for serving LLMs in a cluster.

---

## Hardware Guide

A practical reference for **what your machine can actually run**.

See **[docs/hardware-guide.md](docs/hardware-guide.md)** for:

- VRAM requirements by model size and quantization level.
- Recommended consumer GPUs at each tier.
- Apple Silicon RAM math.
- CPU-only realistic expectations.
- Power, noise, and "is it worth running 24/7" notes.

---

## Communities

Real people fixing real problems in real time.

- [r/LocalLLaMA](https://reddit.com/r/LocalLLaMA) - The single most active local-LLM community. Daily model releases, benchmarks, hardware threads.
- [r/StableDiffusion](https://reddit.com/r/StableDiffusion) - Image-gen counterpart.
- [r/selfhosted](https://reddit.com/r/selfhosted) - Broader self-hosting community; local AI threads are constant.
- [Hugging Face Discord](https://hf.co/join/discord) - Practitioners, model authors, runtime maintainers.
- [Ollama Discord](https://discord.gg/ollama) - Official Ollama community.
- [LM Studio Discord](https://discord.gg/aPQfnNkxGC) - Official LM Studio community.
- [Open WebUI Discord](https://discord.gg/5rJgQTnV4s) - Official Open WebUI community.
- [Hacker News](https://news.ycombinator.com) - Search `local LLM` or `self-hosted AI` weekly.

---

## Newsletters, Blogs & Podcasts

- [Interconnects](https://www.interconnects.ai) - Nathan Lambert's technical, opinionated newsletter on open models.
- [Latent Space](https://www.latent.space) - Podcast + newsletter; frequent local-AI coverage.
- [Simon Willison's Weblog](https://simonwillison.net) - Practical experiments with local models; the best "what actually works today" log.
- [Hugging Face Daily Papers](https://huggingface.co/papers) - Curated paper firehose with discussion threads.
- [The Gradient](https://thegradient.pub) - Long-form essays on ML research; broader than local-AI but often touches it.

---

## Tutorials & Learning

- [Karpathy: nanoGPT](https://github.com/karpathy/nanoGPT) - Train and understand a GPT from scratch.
- [Karpathy: llm.c](https://github.com/karpathy/llm.c) - Same idea, in 1000 lines of C.
- [Karpathy: nanochat](https://github.com/karpathy/nanochat) - Train a chat-tuned LLM end-to-end on a single GPU.
- [Hugging Face Course](https://huggingface.co/learn) - Free, comprehensive, regularly updated.
- [Practical Deep Learning for Coders](https://course.fast.ai) - The fast.ai course. Still the best on-ramp for working engineers.
- [LLM Course (rasbt)](https://github.com/rasbt/LLMs-from-scratch) - Build an LLM from scratch in PyTorch.

---

## Contributing

Pull requests welcome. See **[CONTRIBUTING.md](CONTRIBUTING.md)** for the bar entries must meet and the format to follow.

Quick version:

1. Use the [Add a Project](../../issues/new?template=add-project.yml) issue template if you're not sure.
2. Keep descriptions under one line.
3. Be neutral and concrete. No hype, no marketing copy.
4. Make sure the project meets the [bar](#awesome-local-ai-) - open source or genuinely free local tier, actively maintained, real install path.
