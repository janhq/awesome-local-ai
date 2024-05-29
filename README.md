# [Awesome Local AI](https://github.com/janhq/awesome-local-ai) [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Awesome%20Local%20AI%20-%20a%20collection%20of%20open%20source,%20local%20AI%20tools%20and%20solutions%20by%20@janframework&url=https://github.com/janhq/awesome-local-ai&hashtags=AI,OpenSource)

If you tried [Jan Desktop](https://github.com/janhq/jan?tab=readme-ov-file#download) and liked it, please also check out the following **awesome collection of open source and/or local AI tools and solutions.**

Your contributions are always welcome!

## Lists
- [awesome-local-llms](https://github.com/vince-lam/awesome-local-llms) - Table of open-source local LLM inference projects with their GitHub metrics.
- [llama-police](https://huyenchip.com/llama-police.html) - A list of Open Source LLM Tools from [Chip Huyen](https://huyenchip.com)

## Inference Engine

| Repository                                                      | Description                                                                          | Supported model formats | CPU/GPU Support | UI  | language    | Platform Type |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------ | ----------------------- | --------------- | --- | ----------  | ------------- |
| [llama.cpp](https://github.com/ggerganov/llama.cpp)             | - Inference of LLaMA model in pure C/C++                                             | GGML/GGUF               | Both            | ❌  | C/C++       | Text-Gen      |
| [Nitro](https://github.com/janhq/nitro)                         | - 3MB inference engine embeddable in your apps. Uses Llamacpp and more               | Both                    | Both            | ❌  | Text-Gen    |
| [ollama](https://github.com/jmorganca/ollama)                   | - CLI and local server. Uses Llamacpp                                                | Both                    | Both            | ❌  | Text-Gen    |
| [koboldcpp](https://github.com/LostRuins/koboldcpp)             | - A simple one-file way to run various GGML models with KoboldAI's UI                | GGML                    | Both            | ✅  | C/C++       | Text-Gen      |
| [LoLLMS](https://github.com/ParisNeo/lollms)                    | - Lord of Large Language Models Web User Interface.                                  | Nearly ALL              | Both            | ✅  | Python      | Text-Gen      |
| [ExLlama](https://github.com/turboderp/exllama)                 | - A more memory-efficient rewrite of the HF transformers implementation of Llama     | AutoGPTQ/GPTQ           | GPU             | ✅  | Python/C++  | Text-Gen      |
| [vLLM](https://github.com/vllm-project/vllm)                    | - vLLM is a fast and easy-to-use library for LLM inference and serving.              | GGML/GGUF               | Both            | ❌  | Python      | Text-Gen      |
| [SGLang](https://github.com/sgl-project/sglang)                 | - 3-5x higher throughput than vLLM (Control flow, RadixAttention, KV cache reuse)    | Safetensor / AWQ / GPTQ | GPU             | ❌  | Python      | Text-Gen      |
| [LmDeploy](https://github.com/InternLM/lmdeploy)                | - LMDeploy is a toolkit for compressing, deploying, and serving LLMs.                | Pytorch / Turbomind     | Both            | ❌  | Python/C++  | Text-Gen      |
| [Tensorrt-llm](https://github.com/NVIDIA/TensorRT-LLM)          | - Inference efficiently on NVIDIA GPUs                                               | Python / C++ runtimes   | Both            | ❌  | Python/C++  | Text-Gen      |
| [CTransformers](https://github.com/marella/ctransformers)       | - Python bindings for the Transformer models implemented in C/C++ using GGML library | GGML/GPTQ               | Both            | ❌  | C/C++       | Text-Gen      |
| [llama-cpp-python](https://github.com/abetlen/llama-cpp-python) | - Python bindings for llama.cpp                                                      | GGUF                    | Both            | ❌  | Python      | Text-Gen      |
| [llama2.rs](https://github.com/srush/llama2.rs)                 | - A fast llama2 decoder in pure Rust                                                 | GPTQ                    | CPU             | ❌  | Rust        | Text-Gen      |
| [ExLlamaV2](https://github.com/turboderp/exllamav2)             | - A fast inference library for running LLMs locally on modern consumer-class GPUs    | GPTQ/EXL2               | GPU             | ❌  | Python/C++  | Text-Gen      |
| [LoRAX](https://github.com/predibase/lorax)                     | - Multi-LoRA inference server that scales to 1000s of fine-tuned LLMs                | Safetensor / AWQ / GPTQ | GPU             | ❌  | Python/Rust | Text-Gen      |
| [text-generation-inference](https://github.com/huggingface/text-generation-inference)| - Inference serving toolbox with optimized kernels for each LLM architecture                | Safetensors / AWQ / GPTQ | Both             | ❌  | Python/Rust | Text-Gen      |

## Inference UI

- [oobabooga](https://github.com/oobabooga/text-generation-webui) - A Gradio web UI for Large Language Models.
- [LM Studio](https://lmstudio.ai/) - Discover, download, and run local LLMs.
- [LocalAI](https://github.com/go-skynet/LocalAI) - LocalAI is a drop-in replacement REST API that’s compatible with OpenAI API specifications for local inferencing.
- [FireworksAI](https://app.fireworks.ai/) - Experience the world's fastest LLM inference platform deploy your own at no additional cost.
- [faradav](https://faraday.dev/) - Chat with AI Characters Offline, Runs locally, Zero-configuration.
- [GPT4All](https://gpt4all.io) - A free-to-use, locally running, privacy-aware chatbot.
- [LLMFarm](https://github.com/guinmoon/LLMFarm) - llama and other large language models on iOS and MacOS offline using GGML library.
- [LlamaChat](https://llamachat.app/) - LlamaChat allows you to chat with LLaMa, Alpaca and GPT4All models1 all running locally on your Mac.
- [LLM as a Chatbot Service](https://github.com/deep-diver/LLM-As-Chatbot) - LLM as a Chatbot Service.
- [FuLLMetalAi](https://www.fullmetal.ai/) - Fullmetal.Ai is a distributed network of self-hosted Large Language Models (LLMs).
- [Automatic1111](https://github.com/AUTOMATIC1111/stable-diffusion-webui) - Stable Diffusion web UI.
- [ComfyUI](https://github.com/comfyanonymous/ComfyUI) - A powerful and modular stable diffusion GUI with a graph/nodes interface.
- [Wordflow](https://github.com/poloclub/wordflow) - Run, share, and discover AI prompts in your browsers
- [petals](https://github.com/bigscience-workshop/petals) - Run LLMs at home, BitTorrent-style. Fine-tuning and inference up to 10x faster than offloading.
- [ChatUI](https://github.com/huggingface/chat-ui) - Open source codebase powering the HuggingChat app.
- [AI-Mask](https://github.com/pacoccino/ai-mask) - Browser extension to provide model inference to web apps. Backed by web-llm and transformers.js
- [everything-rag](https://github.com/AstraBert/everything-rag) - Interact with (virtually) any LLM on Hugging Face Hub with an asy-to-use, 100% local Gradio chatbot.
- [LmScript](https://github.com/lucasavila00/LmScript/) - UI for SGLang and Outlines

## Platforms / full solutions

- [H2OAI](https://h2o.ai/#tabs-320f3fc63d-item-aa19ad7787-tab) - H2OGPT The fastest, most accurate AI Cloud Platform.
- [BentoML](https://github.com/bentoml/BentoML) - BentoML is a framework for building reliable, scalable, and cost-efficient AI applications.
- [Predibase](https://predibase.com/) - Serverless LoRA Fine-Tuning and Serving for LLMs.

## Developer tools

- [Jan Framework](https://jan.ai/docs/) - At its core, Jan is a **cross-platform, local-first and AI native** application framework that can be used to build anything.
- [Pinecone](https://www.pinecone.io) - Long-Term Memory for AI.
- [PoplarML](https://www.poplarml.com) - PoplarML enables the deployment of production-ready, scalable ML systems with minimal engineering effort.
- [Datature](https://datature.io) - The All-in-One Platform to Build and Deploy Vision AI.
- [One AI](https://www.oneai.com/) - MAKING GENERATIVE AI BUSINESS-READY.
- [Gooey.AI](https://gooey.ai/) - Create Your Own No Code AI Workflows.
- [Mixo.io](https://mixo.io/?via=futurepedia) - AI website builder.
- [Safurai](https://www.safurai.com) - AI Code Assistant that saves you time in changing, optimizing, and searching code.
- [GitFluence](https://www.gitfluence.com) - The AI-driven solution that helps you quickly find the right command. Get started with Git Command Generator today and save time.
- [Haystack](https://haystack.deepset.ai/) - A framework for building NLP applications (e.g. agents, semantic search, question-answering) with language models.
- [LangChain](https://langchain.com/) - A framework for developing applications powered by language models.
- [gpt4all](https://github.com/nomic-ai/gpt4all) - A chatbot trained on a massive collection of clean assistant data including code, stories and dialogue.
- [LMQL](https://lmql.ai/) - LMQL is a query language for large language models.
- [LlamaIndex](https://www.llamaindex.ai/) - A data framework for building LLM applications over external data.
- [Phoenix](https://phoenix.arize.com/) - Open-source tool for ML observability that runs in your notebook environment, by Arize. Monitor and fine tune LLM, CV and tabular models.
- [trypromptly](https://trypromptly.com/) - Create AI Apps & Chatbots in Minutes.
- [BentoML](https://www.bentoml.com/) - BentoML is the platform for software engineers to build AI products.
- [LiteLLM](https://github.com/BerriAI/litellm) - Call all LLM APIs using the OpenAI format.
- [Tune Studio](https://studio.tune.app/playground) - Playground for software developers to finetune and deploy large language models.

## User Tools
- [llmcord.py](https://github.com/jakobdylanc/discord-llm-chatbot) - Discord LLM Chatbot - Talk to LLMs with your friends!

## Agents

- [SuperAGI](https://superagi.com/) - Opensource AGI Infrastructure.
- [Auto-GPT](https://github.com/Significant-Gravitas/Auto-GPT) - An experimental open-source attempt to make GPT-4 fully autonomous.
- [BabyAGI](https://github.com/yoheinakajima/babyagi) - Baby AGI is an autonomous AI agent developed using Python that operates through OpenAI and Pinecone APIs.
- [AgentGPT](https://agentgpt.reworkd.ai/) -Assemble, configure, and deploy autonomous AI Agents in your browser.
- [HyperWrite](https://www.hyperwriteai.com/) - HyperWrite helps you work smarter, faster, and with ease.
- [AI Agents](https://aiagent.app/) - AI Agent that Power Up Your Productivity.
- [AgentRunner.ai](https://www.agentrunner.ai) - Leverage the power of GPT-4 to create and train fully autonomous AI agents.
- [GPT Engineer](https://github.com/AntonOsika/gpt-engineer) - Specify what you want it to build, the AI asks for clarification, and then builds it.
- [GPT Prompt Engineer](https://github.com/mshumer/gpt-prompt-engineer) - Automated prompt engineering. It generates, tests, and ranks prompts to find the best ones.
- [MetaGPT](https://github.com/geekan/MetaGPT) - The Multi-Agent Framework: Given one line requirement, return PRD, design, tasks, repo.
- [Open Interpreter](https://github.com/KillianLucas/open-interpreter) - Let language models run code. Have your agent write and execute code.
- [CrewAI](https://crewai.io) - Cutting-edge framework for orchestrating role-playing, autonomous AI agents.

## Training

- [FastChat](https://github.com/lm-sys/FastChat) - An open platform for training, serving, and evaluating large language models.
- [DeepSpeed](https://github.com/microsoft/DeepSpeed) - DeepSpeed is a deep learning optimization library that makes distributed training and inference easy, efficient, and effective.
- [BMTrain](https://github.com/OpenBMB/BMTrain) - Efficient Training for Big Models.
- [Alpa](https://github.com/alpa-projects/alpa) - Alpa is a system for training and serving large-scale neural networks.
- [Megatron-LM](https://github.com/NVIDIA/Megatron-LM) - Ongoing research training transformer models at scale.
- [Ludwig](https://github.com/ludwig-ai/ludwig) - Low-code framework for building custom LLMs, neural networks, and other AI models.
- [Nanotron](https://github.com/huggingface/nanotron) - Minimalistic large language model 3D-parallelism training.
- [TRL](https://github.com/huggingface/trl) - Language model alignment with reinforcement learning.
- [PEFT](https://github.com/huggingface/peft) - Parameter efficient fine-tuning (LoRA, DoRA, model merger and more)

## LLM Leaderboard

- [Open LLM Leaderboard](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard) - aims to track, rank and evaluate LLMs and chatbots as they are released.
- [Chatbot Arena Leaderboard](https://huggingface.co/spaces/lmsys/chatbot-arena-leaderboard) - a benchmark platform for large language models (LLMs) that features anonymous, randomized battles in a crowdsourced manner.
- [AlpacaEval Leaderboard](https://tatsu-lab.github.io/alpaca_eval/) - An Automatic Evaluator for Instruction-following Language Models.
- [LLM-Leaderboard-streamlit](https://llm-leaderboard.streamlit.app/) - A joint community effort to create one central leaderboard for LLMs.
- [lmsys.org](https://chat.lmsys.org/) - Benchmarking LLMs in the Wild with Elo Ratings.

## Research

- Attention Is All You Need (2017): Presents the original transformer model. it helps with sequence-to-sequence tasks, such as machine translation. [[Paper]](https://arxiv.org/abs/1706.03762)
- BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding (2018): Helps with language modeling and prediction tasks. [[Paper]](https://arxiv.org/abs/2307.00526)
- FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness (2022): Mechanism to improve transformers. [[paper]](https://arxiv.org/abs/2205.14135)
- Improving Language Understanding by Generative Pre-Training (2019): Paper is authored by OpenAI on GPT. [[paper]](https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf)
- Cramming: Training a Language Model on a Single GPU in One Day (2022): Paper focus on a way too increase the performance by using minimum computing power. [[paper]](https://arxiv.org/abs/2212.14034)
- LaMDA: Language Models for Dialog Applications (2022): LaMDA is a family of Transformer-based neural language models by Google. [[paper]](https://arxiv.org/abs/2201.08239)
- Training language models to follow instructions with human feedback (2022): Use human feedback to align LLMs. [[paper]](https://arxiv.org/abs/2203.02155)
- TurboTransformers: An Efficient GPU Serving System For Transformer Models (PPoPP'21) [[paper]](https://dl.acm.org/doi/pdf/10.1145/3437801.3441578)
- Fast Distributed Inference Serving for Large Language Models (arXiv'23) [[paper]](https://arxiv.org/pdf/2305.05920.pdf)
- An Efficient Sparse Inference Software Accelerator for Transformer-based Language Models on CPUs (arXiv'23) [[paper]](https://arxiv.org/abs/2306.16601)
- Accelerating LLM Inference with Staged Speculative Decoding (arXiv'23) [[paper]](https://arxiv.org/abs/2308.04623)
- ZeRO: Memory optimizations Toward Training Trillion Parameter Models (SC'20) [[paper]](https://ieeexplore.ieee.org/abstract/document/9355301)
- TensorGPT: Efficient Compression of the Embedding Layer in LLMs based on the Tensor-Train Decomposition 2023 [[Paper]](https://arxiv.org/abs/2307.00526)

## Community

- [LocalLLaMA](https://www.reddit.com/r/LocalLLaMA/)
- [singularity](https://www.reddit.com/r/singularity/)
- [ChatGPTCoding](https://www.reddit.com/r/ChatGPTCoding/)
- [StableDiffusion](https://www.reddit.com/r/StableDiffusion/)
- [Hugging Face](https://discord.gg/hugging-face-879548962464493619)
- [JanAI](https://discord.gg/WWjdgYw9Fa)
- [oobabooga](https://www.reddit.com/r/Oobabooga/)
- [GPT4](https://www.reddit.com/r/GPT4/)
- [Artificial Intelligence](https://www.reddit.com/r/artificial/)
- [CrewAI](https://discord.com/invite/X4JWnZnxPb)
