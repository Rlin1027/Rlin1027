# Overview

**Full-stack developer based in Taiwan**, building personal AI agents, vertical tools for the Claude ecosystem, and production systems across robotics and quantitative finance.

My work spans three tracks: **🦞 Claw Ecosystem** — a personal AI agent product line delivered through messaging apps with MCP integration (NanoGemClaw); **🤖 Claude Ecosystem** — vertical plugins and skills that extend Claude Code and Claude cowork into specialized workflows (Claudistotle for philosophy research, ai-agent-architect for AI agent architecture design); and **🎯 Domain Applications** — real-world systems solving problems in robotics (ROSForge) and Taiwan equity valuation (TaiwanStockVECalculator). When I'm not shipping products, I deep-dive into high-impact open-source AI projects — analyzing architectures, adding benchmarking toolkits, and building optimization layers.

---

## Flagship Projects

### 1. NanoGemClaw — Gemini-Powered Google Ecosystem AI Assistant

> `🦞 Claw Ecosystem` · Personal AI Agent  
> **A modular AI assistant on Telegram with MCP Client Bridge, smart routing, and deep Google ecosystem integration.**

<table>
<tr><td>

**What it does:** A full-featured AI assistant powered by Gemini, delivered via Telegram with a 12-page real-time web dashboard. 7 built-in plugins (including Google ecosystem) turn it into a unified personal productivity hub — search Drive files, manage Calendar events, sync Tasks, and query a hybrid RAG knowledge base, all through natural conversation.

**Key differentiators vs NanoClaw (Claude-based):**

| | NanoClaw | NanoGemClaw |
|---|---------|-------------|
| Agent | Claude SDK | Gemini + MCP Client Bridge |
| Bot Framework | node-telegram-bot-api | grammY (type-safe) |
| Messaging | WhatsApp | Telegram Bot API |
| Cost | $100/mo | Free tier (60 req/min) |
| Architecture | Monolith | Modular monorepo (8 packages + 7 plugins) |
| Media | Text only | Photo, Voice, Video, Document |
| Google Integration | None | Drive, Calendar, Tasks, RAG |
| Tests | ~50 | 1,244 tests (54 files, 92% coverage) |

**Highlights:**
- **grammY Bot Framework** — Type-safe, event-driven Telegram integration with rate limiting and message consolidation
- **MCP Client Bridge** — Model Context Protocol support with per-tool whitelist and Zod schema validation
- **Smart Routing** — `preferredPath` intelligently switches between fast path (direct API) and container execution
- **Google Ecosystem** — 7 plugins: OAuth hub, Drive, Calendar (full CRUD), Tasks (bidirectional sync), Drive Knowledge RAG (hybrid search), Discord Reporter, Memorization Service
- **Plugin System** — 6 extension points: Gemini Tools, Message Hooks, Express Routes, IPC Handlers, Background Services, Dashboard Extensions
- **Fast Path** — Direct Gemini API streaming with context caching (75-90% token cost reduction) and native function calling
- **Hybrid Drive RAG** — Pre-indexed embeddings via physical file approach + live Drive search fallback
- **12-page Dashboard** — Overview, Tasks, Calendar, Drive Browser, Knowledge, Analytics, Memory, Logs, Activity, Settings, Schedule, MCP Management
- **i18n 100%** — Full interface support for 8 languages
- **1,244 tests** across 54 files — 92% statement coverage, 84% branch coverage

</td><td width="320">

**Monorepo**
```
nanogemclaw/
├── packages/
│   ├── core/
│   ├── db/
│   ├── gemini/
│   ├── telegram/
│   ├── server/
│   ├── plugin-api/
│   ├── event-bus/
│   └── dashboard/
├── plugins/
│   ├── google-auth/
│   ├── google-drive/
│   ├── google-tasks/
│   ├── google-calendar-rw/
│   ├── drive-knowledge-rag/
│   ├── discord-reporter/
│   └── memorization-service/
├── app/
├── container/
└── docs/
```

**Google Tools (16)**
```
Drive    → search, read, summarize
Tasks    → create, complete, list
Calendar → create, list, update,
           delete, check_availability
RAG      → search_knowledge
Discord  → daily/weekly reports
```

</td></tr>
</table>

```bash
git clone https://github.com/Rlin1027/NanoGemClaw.git
cp .env.example .env    # Add TELEGRAM_BOT_TOKEN + GEMINI_API_KEY
npm install && npm run dev
```

[![Repo](https://img.shields.io/badge/GitHub-NanoGemClaw-181717?style=flat&logo=github)](https://github.com/Rlin1027/NanoGemClaw)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini-886FBF?style=flat&logo=googlegemini&logoColor=white)
![Telegram](https://img.shields.io/badge/Telegram-26A5E4?style=flat&logo=telegram&logoColor=white)
![Google](https://img.shields.io/badge/Google_APIs-4285F4?style=flat&logo=google&logoColor=white)

---

### 2. Claudistotle — Philosophy Research Plugin for Claude Code

> `🤖 Claude Ecosystem` · Academic Research Pipeline  
> **A full-pipeline philosophy research assistant: from topic idea to peer-reviewed paper, entirely inside Claude Code.**

<table>
<tr><td>

**What it does:** Claudistotle takes you end-to-end from a rough research question to a polished academic paper — searching 8+ academic databases, synthesizing a literature review with verified citations (never fabricates references), writing structured academic prose, and simulating three-round peer review. Built as a Claude Code plugin.

**Pipeline:**

```
Topic idea → Research design → Literature review → Draft → Peer review → Paper
```

**Highlights:**
- **8+ academic databases** — Semantic Scholar, OpenAlex, CORE, arXiv, PhilPapers, Stanford Encyclopedia, Internet Encyclopedia, Notre Dame Philosophical Reviews
- **Citation integrity** — every reference verified against CrossRef; fabricated citations are impossible by design (BibTeX hooks validate metadata provenance before any `.bib` is written)
- **6-phase literature review** — environment check → domain decomposition → parallel database search → synthesis planning → section writing → assembly with DOCX export
- **Three-round peer review simulation** — two AI personas (Athena the reviewer, Calliope the reviser) iterate on argument validity, evidence quality, and writing clarity
- **Autopilot with self-healing** — cautious / moderate / full autonomy modes; automatic retry on quality gate failures
- **Text commentary** — close reading and logical annotation of primary philosophical texts, auto-integrated into your draft
- **Resumable** — interrupted sessions resume from `PROGRESS.md`
- **Extends [PhilLit](https://github.com/AI-4-Phi/PhilLit)** — the multi-agent research workflow from Syracuse University & University of Hamburg

</td><td width="320">

**Commands (12)**
```
setup
help
research-design
literature-review
text-commentary
draft
peer-review
refine
validate
feedback
autopilot
philosophy-research
```

**Output**
```
reviews/[project]/
├── research-proposal.md
├── literature-review-final.md
├── literature-all.bib
├── argument-skeleton.md
├── paper-draft.md
├── change-record.md
├── PROGRESS.md
└── sources/
    ├── primary/
    └── secondary/
```

</td></tr>
</table>

```bash
# Install
/plugin marketplace add Rlin1027/claudistotle
/plugin install claudistotle@claudistotle

# Use
/claudistotle:setup
/claudistotle:literature-review
```

[![Repo](https://img.shields.io/badge/GitHub-Claudistotle-181717?style=flat&logo=github)](https://github.com/Rlin1027/claudistotle)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-Plugin-7C3AED?logo=anthropic&logoColor=white)
![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)

---

### 3. ai-agent-architect — AI Agent Architecture Designer

> `🤖 Claude Ecosystem` · Socratic Agent Design Pipeline  
> **A Claude cowork skill that interviews you before recommending any AI agent architecture — grounding every design decision in actual requirements.**

<table>
<tr><td>

**Problem it solves:** Most AI agent failures come from choosing patterns based on technical appeal rather than real business requirements. Teams jump to "multi-agent system" before understanding what problem they're solving.

**Approach:** A structured five-phase pipeline based on Anthropic's *Building Effective Agents* framework. It runs a Socratic deep interview across four clarity dimensions, scores ambiguity in real time, and only produces a recommendation once the problem is actually understood.

**Highlights:**
- **Five-phase pipeline** — Deep Interview → Recommendation → Blueprint → Functional Modules → Execution Bridge, each with a quality gate
- **Four-dimension scoring** — Goal (35%) / Constraints (25%) / Domain (25%) / Success Criteria (15%), live progress bars every round
- **Ambiguity gate** — pipeline won't exit Phase 1 until ambiguity ≤ 20% (soft cap Round 8, hard cap Round 12)
- **Challenge modes** — auto-triggered Contrarian / Simplifier / Ontologist questions break circular answers and surface hidden assumptions
- **Decision matrix** — four-axis evaluation (control × complexity × resources × expertise) selects from 8 architecture patterns including hybrid strategies
- **Single-agent first** — multi-agent systems (10–15× more tokens) only recommended when interview evidence clearly shows a single agent is insufficient
- **Greenfield & brownfield** — automatically shifts questioning when you mention migration, legacy integration, or rollback criteria
- **Implementation-ready output** — blueprint with Mermaid architecture diagram, PRD, technical spec, cost analysis spreadsheet, risk matrix, evaluation plan, and starter prototype

</td><td width="320">

**Phases**
```
Phase 1 · Deep Interview
  └ gate: ambiguity ≤ 20%
Phase 2 · Recommendation
  └ gate: user confirms
Phase 3 · Blueprint
Phase 4 · Functional Modules
Phase 5 · Execution Bridge
```

**Patterns (8)**
```
Single Agent
Routing Workflow
Sequential Workflow
Parallel Workflow
Hierarchical Multi-Agent
Collaborative Multi-Agent
Evaluator-Optimizer
Hybrid Strategies
```

**Artifacts**
```
interview-spec.md
ai-agent-blueprint.md
prd.md
tech-spec.md
cost-analysis.xlsx
risk-matrix.md
eval-plan.md
prototype/
```

</td></tr>
</table>

```bash
git clone https://github.com/Rlin1027/ai-agent-architect.git
# Place into your Claude cowork skills directory
# Trigger: mention "AI agent design" or "agent architecture" in your prompt
```

[![Repo](https://img.shields.io/badge/GitHub-ai--agent--architect-181717?style=flat&logo=github)](https://github.com/Rlin1027/ai-agent-architect)
![Claude](https://img.shields.io/badge/Claude-cowork-orange)
![Model](https://img.shields.io/badge/requires-Sonnet%2B-blueviolet)
![Based On](https://img.shields.io/badge/based_on-Building_Effective_Agents-red)

---

## Domain Applications

### ROSForge — AI-Powered ROS1 to ROS2 Migration Engine

> `🎯 Domain Applications` · Robotics  
> **The first AI-driven tool to automate legacy robotics code migration.**

<table>
<tr><td>

**Problem:** Migrating a mid-size ROS1 package (~5K-10K LoC) takes a senior engineer 2-4 weeks of manual refactoring. With ROS1 Noetic EOL (May 2025), thousands of packages face abandonment.

**Solution:** One command to reforge your legacy robotics packages. ROSForge uses LLMs to *understand* code semantics — not just regex-replace — and delivers end-to-end migration with automatic build verification and fix loops.

**What makes it unique:**
- **BYOM (Bring Your Own Model)** — freely switch between Claude, Gemini, and OpenAI
- **Full-spectrum migration** — C++ (roscpp→rclcpp), Python (rospy→rclpy), Launch files (XML→Python), CMakeLists.txt, package.xml, msg/srv definitions
- **Validate-Fix loop** — auto `colcon build` + AI-driven error repair
- **Interactive mode** — pause at critical steps for human review
- **Workspace-level batch migration** with cross-package dependency resolution
- **Custom rules** via `.rosforge/rules.yaml`

</td><td width="320">

**Stack**
```
Python 3.14 | Click CLI
Pipeline Architecture
├─ Ingest (Parsers)
├─ Analyze (Deps)
├─ Transform (AI)
├─ Validate (Build)
└─ Report (Diff)
```

**Pipeline**
```
rosforge migrate ./pkg
  ↓ Parse AST/IR
  ↓ Resolve dependencies
  ↓ AI transform (BYOM)
  ↓ colcon build
  ↓ Auto-fix if failed
  ↓ Generate report
```

</td></tr>
</table>

```bash
pip install rosforge
rosforge migrate ./my_ros1_package          # End-to-end migration
rosforge analyze ./my_ros1_package          # Analysis only (no changes)
rosforge config set engine claude-code      # Switch AI engine
```

[![Repo](https://img.shields.io/badge/GitHub-ROSForge-181717?style=flat&logo=github)](https://github.com/Rlin1027/ROSForge)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![ROS](https://img.shields.io/badge/ROS-22314E?style=flat&logo=ros&logoColor=white)

---

### TaiwanStockVECalculator — 7-Model Stock Valuation System

> `🎯 Domain Applications` · Quantitative Finance  
> **Quantitative valuation engine for Taiwan stocks with LLM-enhanced classification and adaptive feedback loops.**

<table>
<tr><td>

**What it does:** Input a stock ticker, get fair value estimates from 7 independent models — weighted by industry classification, validated by backtesting, and auto-adjusted through feedback loops.

**7 Valuation Models:**

| Model | Method |
|-------|--------|
| A | Multi-stage DCF (Discounted Cash Flow) |
| B | Dividend Yield + Gordon Growth Model |
| C | PER (Price-to-Earnings Ratio) River Chart |
| D | PBR (Price-to-Book Ratio) |
| E | CapEx Forward-Looking Valuation |
| F | EV/EBITDA Enterprise Value Multiples |
| G | PSR (Price-to-Sales Ratio) |

**System features:**
- **3 interfaces** — CLI (colored terminal), HTTP API (Express), n8n automation workflow
- **LLM smart classification** — auto-categorize stocks by industry with guardrails
- **Backtest engine** — 90d/180d accuracy validation with hit rate, MAE metrics
- **Adaptive weights** — feedback loop adjusts model weights based on backtest accuracy per category
- **Portfolio management** — sector allocation, risk metrics, performance tracking
- **Alert system** — price/valuation/classification change triggers → Telegram/Email push

</td><td width="320">

**Architecture**
```
src/
├── api/         # FinMind API
├── models/      # 7 valuation models
│   ├── dcf.js
│   ├── dividend.js
│   ├── per.js
│   ├── pbr.js
│   ├── capex.js
│   ├── ev-ebitda.js
│   └── psr.js
├── llm/         # LLM guardrails
├── backtest/    # Accuracy engine
├── feedback/    # Adaptive weights
├── portfolio/   # Analytics
└── report/      # Synthesis
```

**Data Pipeline**
```
FinMind API (8 datasets)
  ↓ Parallel fetch
7 Models (parallel calc)
  ↓ Smart weighting
LLM Classification
  ↓ Backtest feedback
Final Recommendation
  ↓ n8n automation
Telegram / Email
```

</td></tr>
</table>

```bash
node src/index.js 2330              # CLI: Analyze TSMC
node src/server.js                  # Start HTTP API
curl -X POST localhost:3000/api/analyze/2330
```

[![Repo](https://img.shields.io/badge/GitHub-TaiwanStockVECalculator-181717?style=flat&logo=github)](https://github.com/Rlin1027/TaiwanStockVECalculator)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Express](https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat&logo=n8n&logoColor=white)

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

## Other Projects

### AI & Developer Tools

| Project | Description | Stack |
|---------|-------------|-------|
| [repo2prompt](https://github.com/Rlin1027/repo2prompt) | Convert git repos to LLM-friendly prompts with token estimation | Python |
| [pocketflow-enhanced](https://github.com/Rlin1027/pocketflow-enhanced) | Visualization, tracing & caching extensions for the 100-line LLM framework | Python |

### Quantitative Finance & Full-Stack

| Project | Description | Stack |
|---------|-------------|-------|
| [heritage-hunter](https://github.com/Rlin1027/heritage-hunter) | Gamified unclaimed land search engine for Taiwan with interactive map | Next.js, Supabase |
| [fire-calculator](https://github.com/Rlin1027/fire-calculator) | Financial Independence / Retire Early calculator | TypeScript |
| [n8n-portfolio](https://github.com/Rlin1027/n8n-portfolio) | Production-grade automation workflows with AI, RAG & data pipelines | n8n, Python |
| [SLOTprototype](https://github.com/Rlin1027/SLOTprototype) | Fortune God Slots — Chinese themed slot machine prototype | TypeScript |

---

## AI/ML Research Toolkit

I systematically enhance popular open-source AI projects by adding **architecture analysis**, **benchmarking frameworks**, and **optimization toolkits**.

> **25+ projects enhanced** across LLMs, TTS, Video, Agents, and Training Infrastructure — totaling **3,000+ tests** written.

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
