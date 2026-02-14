# Overview

**Full-stack developer based in Taiwan**, building at the intersection of AI research, quantitative finance, and automation.

I deep-dive into high-impact open-source AI projects — analyzing architectures, adding benchmarking toolkits, and building optimization layers. When I'm not dissecting ML models, I build production systems: from a 7-model stock valuation engine to n8n automation pipelines and gamified civic-data platforms.

---

## What I Build

**AI/ML Research Toolkits** — Architecture analysis, benchmarking & optimization for 25+ popular open-source AI projects (LLMs, TTS, Video, Agents)
**Quantitative Finance** — Multi-model stock valuation systems, ETF dashboards, automated weekly reports with LLM-enhanced analysis
**AI Assistants & Developer Tools** — Telegram bots with Gemini agents, repo-to-prompt converters, LLM framework extensions
**Automation** — n8n workflows for data pipelines, music rendering, RAG systems, and fault-tolerant batch processing
**Full-Stack Apps** — Real-time dashboards, gamified civic data platforms, playlist organizers, visual storytelling tools

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat&logo=supabase&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat&logo=n8n&logoColor=white)

---

## Featured Projects

### AI & Developer Tools

| Project | Description | Stack |
|---------|-------------|-------|
| [NanoGemClaw](https://github.com/Rlin1027/NanoGemClaw) | Personal AI assistant — Telegram bot with containerized Gemini agents, real-time dashboard, scheduled tasks & knowledge base | TypeScript, Express, Socket.IO, SQLite |
| [repo2prompt](https://github.com/Rlin1027/repo2prompt) | Convert git repositories to LLM-friendly prompts with token estimation and smart filtering | Python |
| [pocketflow-enhanced](https://github.com/Rlin1027/pocketflow-enhanced) | Visualization, tracing & caching extensions for the 100-line LLM framework | Python |

### Quantitative Finance

| Project | Description | Stack |
|---------|-------------|-------|
| [TaiwanStockVECalculator](https://github.com/Rlin1027/TaiwanStockVECalculator) | 7-model stock valuation system (DCF, PER, PBR, Dividend, CapEx, EV/EBITDA, PSR) with LLM classification, backtest feedback loop, n8n automation & Telegram/Email reports | JavaScript, Express, SQLite, n8n |
| [heritage-hunter](https://github.com/Rlin1027/heritage-hunter) | Gamified unclaimed land search engine for Taiwan with interactive map | Next.js, TypeScript, Supabase |
| [fire-calculator](https://github.com/Rlin1027/fire-calculator) | Financial Independence / Retire Early calculator | TypeScript |

### Automation & Full-Stack

| Project | Description | Stack |
|---------|-------------|-------|
| [n8n-portfolio](https://github.com/Rlin1027/n8n-portfolio) | Production-grade automation workflows with AI, RAG & data pipelines | n8n, Python |
| [spotify-organizer](https://github.com/Rlin1027/spotify-organizer) | Smart playlist organizer — sort by decade, genre, or mood | TypeScript, Spotify API |
| [visual-storyteller](https://github.com/Rlin1027/visual-storyteller) | AI visual storytelling app that generates narratives from images | TypeScript, GPT-4 Vision |

---

## AI/ML Research Toolkit

I systematically enhance popular open-source AI projects by adding **architecture analysis**, **benchmarking frameworks**, and **optimization toolkits**. Each enhanced repo includes comprehensive test suites, detailed documentation, and practical utilities that the original project lacks.

> **25+ projects enhanced** across LLMs, speech synthesis, video generation, AI agents, and training infrastructure — totaling **3,000+ tests** written.

<details>
<summary><b>LLM & Language Models</b> — 8 projects</summary>

| Project | Original | What's Added |
|---------|----------|-------------|
| [nanochat-enhanced](https://github.com/Rlin1027/nanochat-enhanced) | Karpathy's nanoGPT (43k stars) | Architecture analysis, optimization toolkit & benchmarking — 167 tests |
| [nano-vllm-enhanced](https://github.com/Rlin1027/nano-vllm-enhanced) | nano-vllm | Analytics, advanced sampling & optimization — 160 tests |
| [grpo-zero-enhanced](https://github.com/Rlin1027/grpo-zero-enhanced) | DeepSeek R1 GRPO | Analytics, Math24/logic tasks, algorithm variants — 105 tests |
| [hrm-enhanced](https://github.com/Rlin1027/hrm-enhanced) | Hierarchical Reasoning Model | Analytics, puzzle generation & advanced algorithms — 147 tests |
| [lingua-enhanced](https://github.com/Rlin1027/lingua-enhanced) | Meta Lingua | Architecture analysis, config library & training estimation — 137 tests |
| [minbpe-enhanced](https://github.com/Rlin1027/minbpe-enhanced) | Karpathy's minbpe | WordPiece/Unigram/BPE-Dropout algorithms & visualization — 96 tests |
| [picoGPT-enhanced](https://github.com/Rlin1027/picoGPT-enhanced) | picoGPT | Sampling, KV-Cache & interactive mode for GPT-2 in NumPy |
| [tiny-llm-enhanced](https://github.com/Rlin1027/tiny-llm-enhanced) | LLM Serving Course | Architecture analysis, serving strategy & benchmarking |

</details>

<details>
<summary><b>AI Agents & MCP</b> — 8 projects</summary>

| Project | Original | What's Added |
|---------|----------|-------------|
| [swarm-enhanced](https://github.com/Rlin1027/swarm-enhanced) | OpenAI Swarm (21k stars) | Multi-agent analysis, optimization & benchmarking — 131 tests |
| [aisuite-enhanced](https://github.com/Rlin1027/aisuite-enhanced) | Andrew Ng's aisuite (13.5k stars) | Provider analysis, intelligent routing & benchmarking |
| [fastapi-mcp-enhanced](https://github.com/Rlin1027/fastapi-mcp-enhanced) | fastapi-mcp (11.5k stars) | Endpoint analysis, intelligent routing & conversion benchmarking |
| [claude-agent-sdk-enhanced](https://github.com/Rlin1027/claude-agent-sdk-enhanced) | Anthropic Agent SDK (4.8k stars) | Configuration analysis, optimization & benchmarking |
| [langchain-mcp-enhanced](https://github.com/Rlin1027/langchain-mcp-enhanced) | LangChain MCP Adapters | Configuration analysis, performance optimization — 211 tests |
| [mcpo-enhanced](https://github.com/Rlin1027/mcpo-enhanced) | mcpo (MCP-to-OpenAPI) | Config analysis, intelligent routing & benchmarking |
| [claude-usage-monitor-enhanced](https://github.com/Rlin1027/claude-usage-monitor-enhanced) | Claude Code Usage Monitor | Usage analysis, cost optimization & benchmarking — 128 tests |
| [simple-evals-enhanced](https://github.com/Rlin1027/simple-evals-enhanced) | OpenAI simple-evals | Analysis, statistics & reporting for LLM evaluations |

</details>

<details>
<summary><b>Vision & Video Generation</b> — 5 projects</summary>

| Project | Original | What's Added |
|---------|----------|-------------|
| [framepack-enhanced](https://github.com/Rlin1027/framepack-enhanced) | FramePack (16.6k stars) | Architecture analysis, optimization & benchmarking — 227 tests |
| [omost-enhanced](https://github.com/Rlin1027/omost-enhanced) | Omost (7.6k stars) | Canvas analysis, pipeline optimization & benchmarking — 148 tests |
| [ltx-video-enhanced](https://github.com/Rlin1027/ltx-video-enhanced) | LTX-Video (9.3k stars) | Architecture analysis, optimization & benchmarking |
| [vjepa2-enhanced](https://github.com/Rlin1027/vjepa2-enhanced) | Meta V-JEPA 2 | Architecture analysis, config library & benchmarking |
| [mambaout-enhanced](https://github.com/Rlin1027/mambaout-enhanced) | MambaOut (CVPR 2025) | Architecture analysis, model variants & benchmarking — 113 tests |

</details>

<details>
<summary><b>Speech & Audio</b> — 4 projects</summary>

| Project | Original | What's Added |
|---------|----------|-------------|
| [dia-enhanced](https://github.com/Rlin1027/dia-enhanced) | Dia TTS (19.1k stars) | Architecture analysis, optimization & benchmarking — 172 tests |
| [csm-enhanced](https://github.com/Rlin1027/csm-enhanced) | Sesame CSM (14.5k stars) | Architecture analysis, inference optimization & benchmarking |
| [pocket-tts-enhanced](https://github.com/Rlin1027/pocket-tts-enhanced) | Kyutai Pocket TTS (3.1k stars) | Synthesis profiling & hardware benchmarking |
| [speech-to-speech-enhanced](https://github.com/Rlin1027/speech-to-speech-enhanced) | HuggingFace S2S | Pipeline analysis, config management & benchmarking |

</details>

<details>
<summary><b>Training Infrastructure & Architecture</b> — 5 projects</summary>

| Project | Original | What's Added |
|---------|----------|-------------|
| [self-forcing-enhanced](https://github.com/Rlin1027/self-forcing-enhanced) | Self-Forcing (NeurIPS 2025 Spotlight) | Training analysis, pipeline optimization & benchmarking |
| [dualpipe-enhanced](https://github.com/Rlin1027/dualpipe-enhanced) | DualPipe (DeepSeek V3/R1) | Pipeline analysis, schedule simulation & benchmarking — 132 tests |
| [nano-graphrag-enhanced](https://github.com/Rlin1027/nano-graphrag-enhanced) | nano-graphrag (GraphRAG) | Graph analysis, retrieval strategies & benchmarking |
| [efficient-kan-enhanced](https://github.com/Rlin1027/efficient-kan-enhanced) | efficient-kan (KAN) | Analysis, visualization & training utilities |
| [minimalRL-enhanced](https://github.com/Rlin1027/minimalRL-enhanced) | minimalRL (12 RL algorithms) | Logging, visualization & experiment tracking |

</details>

---

## GitHub Stats

<p>
  <img height="160" src="https://github-readme-stats-one-nu-91.vercel.app/api?username=Rlin1027&show_icons=true&theme=default&hide_border=true&count_private=true" />
  <img height="160" src="https://github-readme-stats-one-nu-91.vercel.app/api/top-langs/?username=Rlin1027&layout=compact&theme=default&hide_border=true" />
</p>
