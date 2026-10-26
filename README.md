<div align="center">

# 🤖 Awesome Agent

**A carefully curated list of AI Agent resources — frameworks, tools, memory systems, benchmarks, papers and learning materials**

*Continuously collected · Manually verified · Opinionated curation*

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](CONTRIBUTING.md)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Last Updated](https://img.shields.io/badge/last%20updated-March%202026-blue?style=flat-square)](https://github.com/EthanYolo01/Awesome-Agent/commits/main)
[![Stars](https://img.shields.io/github/stars/EthanYolo01/Awesome-Agent?style=flat-square)](https://github.com/EthanYolo01/Awesome-Agent/stargazers)

> **Opinionated curation over exhaustive listing.**
> Every entry was reviewed and link-verified. We tell you *why* each resource matters and *when* to use it.

**AI Agent Landscape (March 2026):** 🗂️ 4.3M+ AI-related GitHub repos &nbsp;·&nbsp; 📈 178% YoY growth in LLM Agent projects &nbsp;·&nbsp; 🏭 68% of production agents use open source frameworks &nbsp;·&nbsp; 🌐 MCP + A2A emerging as agent interoperability standards

---

🌐 Language / 语言切换：**English** | [中文](README_CN.md)

</div>

---

## 📋 Table of Contents

- [🏁 What is an AI Agent?](#-what-is-an-ai-agent)
- [⏳ Timeline](#-timeline)
- [🧠 Core Concepts Quick Reference](#-core-concepts-quick-reference)
- [🏗️ Agent Framework Landscape](#️-agent-framework-landscape)
  - [General-Purpose Agent Frameworks](#general-purpose-agent-frameworks)
  - [Multi-Agent Collaboration Frameworks](#multi-agent-collaboration-frameworks)
  - [Lightweight & Minimal Frameworks](#lightweight--minimal-frameworks)
  - [Enterprise Frameworks](#enterprise-frameworks)
- [🦞 Personal AI Agents](#-personal-ai-agents)
- [💻 Code Agents](#-code-agents)
- [🌐 Browser & Computer Control Agents](#-browser--computer-control-agents)
- [🔬 Research & Deep Exploration Agents](#-research--deep-exploration-agents)
- [🧠 Agent Memory Systems](#-agent-memory-systems)
- [🛠️ Tools & Integrations](#️-tools--integrations)
  - [Tool-Calling Frameworks](#tool-calling-frameworks)
  - [Code Execution Sandboxes](#code-execution-sandboxes)
  - [Local Model Running](#local-model-running)
  - [Agent Communication Protocols](#agent-communication-protocols)
- [📊 Observability, Evaluation & Benchmarks](#-observability-evaluation--benchmarks)
- [🔒 Agent Security](#-agent-security)
- [🤖 Embodied Agents & Robotics](#-embodied-agents--robotics)
- [📖 Tutorials, Blogs & Articles](#-tutorials-blogs--articles)
- [📚 Papers & Academic Resources](#-papers--academic-resources)
- [🗺️ Related Awesome Lists](#️-related-awesome-lists)

---

## 🏁 What is an AI Agent?

An **AI Agent** is an AI system that perceives its environment, plans autonomously, calls tools, and executes multi-step tasks to achieve goals. Unlike single-turn LLM calls, agents make active decisions, use tools, maintain context, and complete complex tasks without step-by-step human guidance.

**One-line summary:** A plain LLM = answer one question at a time; an Agent = understand the goal → make a plan → call tools → take action → verify results → loop until done.

**Core difference between an Agent and a plain LLM call:**

| Dimension | Plain LLM | AI Agent |
|---|---|---|
| **Task scope** | Single-turn Q&A | Multi-step, long-horizon tasks |
| **Tool use** | None | Can call search, code execution, APIs, browsers, etc. |
| **Memory** | Current context window only | Persistent cross-session memory |
| **Planning** | None | Can decompose tasks and form execution plans |
| **Autonomy** | Passive response | Active decision-making and action |
| **Error recovery** | None | Can detect errors and retry |

**Three common Agent patterns:**

```
ReAct (most common):
  Thought → Action → Observation → loop

Planner-Executor:
  Make a plan → execute step by step → verify results

Multi-Agent collaboration:
  Coordinator → dispatch to specialist sub-agents → aggregate results
```

---

## ⏳ Timeline

```
2022    ──  ReAct paper (Yao et al.) introduces Reasoning + Acting paradigm
            Chain-of-Thought lays the foundation for agent reasoning
            WebGPT demonstrates LLM + search tool possibilities

Early   ──  AutoGPT goes viral (100K+ stars) — brings "autonomous agents"
2023        into public consciousness
            BabyAGI: prototype of task-driven autonomous agents
            HuggingGPT / TaskMatrix: multi-model collaboration proposed
            LangChain becomes the de facto agent framework standard

Mid     ──  MetaGPT: simulates a software company team with multiple agents
2023        AutoGen (Microsoft): conversation-driven multi-agent framework
            Voyager: embodied agent that continuously learns in Minecraft

2024    ──  OpenDevin (now OpenHands): open source autonomous software eng. agent
            SWE-bench becomes the standard benchmark for code agents
            Devin (Cognition): first commercial code agent, sparks industry attention
            LangGraph: graph state machine for precise complex workflow control
            Claude Computer Use: Anthropic launches computer control (beta)
            MCP protocol: standardized tool-calling for agents

2025    ──  OpenAI Agents SDK: official multi-agent orchestration framework
            Google ADK (Agent Development Kit) launches
            Mastra: TypeScript agent framework rises quickly
            Pydantic AI: type-safe Python agent framework
            Agent benchmarks mature: GAIA, OSWorld, SWE-bench Verified
            A2A protocol (Google): inter-agent communication standardization attempt
            MCP donated to Linux Foundation as a vendor-neutral open standard
            AutoGen + Semantic Kernel merge into Microsoft Agent Framework (Oct 2025)
            Flowise acquired by Workday (Aug 2025)

Early   ──  Claude Code reaches SWE-bench Verified 80.9% — code agent breakthrough
2026        Gemini CLI with native MCP support
            OpenClaw explodes (9K → 210K+ stars in 60 days)
            VoltAgent, Mastra and other TypeScript frameworks surge
            MemOS, Letta and other memory OSes become the new hotspot
            Multi-agent collaboration becomes production mainstream
            (Gartner: 1/3 of deployments will be multi-agent by 2027)
```

---

## 🧠 Core Concepts Quick Reference

### Four Core Agent Capability Modules

| Module | Description | Typical Implementation |
|---|---|---|
| **Perception** | Receive inputs: text, images, audio, tool returns, environment state | Multimodal models, visual understanding |
| **Planning** | Decompose tasks, form steps, handle uncertainty | ReAct, CoT, Tree-of-Thought, MCTS |
| **Memory** | Retain information across steps and sessions | Vector DBs, knowledge graphs, context compression |
| **Action** | Call tools, generate code, control systems, communicate with other agents | Tool calling, code execution, MCP, APIs |

### Memory Types

| Type | Description | Human Analogy |
|---|---|---|
| **Working Memory** | Information in the current context window | Short-term memory |
| **Episodic Memory** | History logs of conversations and events | Specific experiences |
| **Semantic Memory** | Distilled knowledge and facts | Knowledge system |
| **Procedural Memory** | Methods and skills for executing tasks | Muscle memory |
| **Parametric Memory** | Knowledge encoded in model weights | Instinct and intuition |

### Common Agent Architecture Patterns

**ReAct (Reasoning + Acting)** — the most widely adopted paradigm:
```
User: "Research the 2026 AI agent market size"
Thought: Need to search for the latest data
Action: search("2026 AI agent market size")
Observation: [search results]
Thought: Found the data, need to analyze further
Action: analyze(data)
... final answer
```

**Planner-Executor** — plan first then execute; best for deterministic tasks.

**Reflexion** — agent self-critiques and improves its own output; best for high-quality output requirements.

**Multi-Agent Collaboration** — specialization: one agent searches, one analyzes, one writes, one reviews.

---

## 🏗️ Agent Framework Landscape

### Framework Selection Decision Tree

```
Your need is...
├── Rapid prototyping?
│   └── CrewAI or OpenAI Agents SDK
├── Complex state machine + long-term maintenance?
│   └── LangGraph
├── Type safety + high reliability?
│   └── Pydantic AI
├── TypeScript-first?
│   └── Mastra or VoltAgent
├── Enterprise .NET/Azure ecosystem?
│   └── Microsoft Agent Framework
├── RAG-heavy applications?
│   └── LlamaIndex Agents
├── Minimal dependencies + learning?
│   └── smolagents
└── Full customization + data sovereignty?
    └── Build from scratch or OpenClaw
```

### General-Purpose Agent Frameworks

| Framework | Language | GitHub | Stars | Description |
|---|---|---|---|---|
| ⭐ **LangGraph** | Python | [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) | 13K+ | **Top choice for complex workflows.** Graph state machine: nodes + edges define execution flow; built-in checkpointing, resume-from-breakpoint, human-in-the-loop; deep LangSmith observability. 30–40% more control than simple chains, at the cost of a steeper learning curve |
| ⭐ **OpenAI Agents SDK** | Python | [openai/openai-agents-python](https://github.com/openai/openai-agents-python) | 6K+ | OpenAI's official multi-agent orchestration framework. Three core primitives: Agents, Handoffs, Guardrails; built-in tracing; lowest-friction choice if your stack centers on OpenAI |
| ⭐ **Google ADK** | Python / Java | [google/adk-python](https://github.com/google/adk-python) | 8K+ | Google's official Agent Development Kit. Multi-agent orchestration, built-in Gemini integration; Vertex AI native deployment; code-first design with concise tool definitions |
| **Pydantic AI** | Python | [pydantic/pydantic-ai](https://github.com/pydantic/pydantic-ai) | 10K+ | From the Pydantic team. Type safety is the core differentiator — full type validation on all tool inputs and outputs; dependency injection; model-agnostic. High production code quality, fewer runtime errors |
| **Mastra** | TypeScript | [mastra-ai/mastra](https://github.com/mastra-ai/mastra) | 20K+ | Best choice for TypeScript developers. Built-in tool library, memory, RAG, workflows, observability; official MCP integration; convention over configuration |
| **VoltAgent** | TypeScript | [VoltAgent/voltagent](https://github.com/voltagent/voltagent) | 3K+ | Open source TypeScript agent framework with built-in LLM observability; sub-agent system; MCP client support; ideal for full-stack Node.js projects |
| **Agno** | Python | [agno-agi/agno](https://github.com/agno-agi/agno) | 25K+ | Ultra-fast Agent SDK (3.77μs agent instantiation, industry fastest); 100+ LLMs; built-in memory, knowledge base, tools, multi-agent teams |
| **AutoGPT** | Python | [Significant-Gravitas/AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 182K+ | **The project that first brought "autonomous agents" into public consciousness.** Evolved from an experimental CLI into a full agent platform: CoPilot assistant, visual workflow builder, E2B sandboxed code execution, MCP server discovery, agent marketplace; still actively releasing in March 2026 (v0.6.50) |
| **smolagents** | Python | [huggingface/smolagents](https://github.com/huggingface/smolagents) | 15K+ | By HuggingFace. Minimal design — ~1,000 lines of core code, readable in an afternoon; Code Agent paradigm (generates and runs Python directly); model-agnostic; ideal for learning agent internals or rapid prototyping |
| **Haystack** | Python | [deepset-ai/haystack](https://github.com/deepset-ai/haystack) | 18K+ | NLP Pipeline and RAG-oriented; composable Pipeline design; mature choice for production retrieval-augmented applications |

### Multi-Agent Collaboration Frameworks

| Framework | GitHub | Stars | Description |
|---|---|---|---|
| ⭐ **CrewAI** | [crewAIInc/crewAI](https://github.com/crewAIInc/crewAI) | 46K+ | **Easiest multi-agent framework to get started with.** Role-playing metaphor: each agent has Role, Goal, Backstory; intuitive Team → Task → Agent mapping. Great for content generation, research analysis, customer service routing. CrewAI AMP enterprise edition includes Salesforce / Gmail / Slack triggers |
| **Microsoft Agent Framework (AutoGen successor)** | [microsoft/autogen](https://github.com/microsoft/autogen) | 38K+ | In October 2025, Microsoft **merged** AutoGen and Semantic Kernel into the unified Microsoft Agent Framework (GA target Q1 2026). AutoGen is now in maintenance mode, accepting bug fixes only; new projects should use Microsoft Agent Framework + Azure AI Foundry integration. Classic patterns like Group Chat and Sequential Chat remain available |
| **MetaGPT** | [geekan/MetaGPT](https://github.com/geekan/MetaGPT) | 57K+ | Simulates a software company team: product manager, architect, engineer, tester each play a role. Give it one line of requirements; it returns PRD, design doc, code, and CI config. The benchmark for software engineering pipeline automation |
| **OpenAgents** | [OpenAgentsInc/openagents](https://github.com/OpenAgentsInc/openagents) | 1.7K+ | Native support for both MCP and A2A protocols; persistent agent networks; modular extension system. Currently the only framework with native dual support for both major agent interoperability protocols |
| **AG2** | [ag2ai/ag2](https://github.com/ag2ai/ag2) | 36K+ | Continuation project by the original AutoGen creators (community fork); preserves AutoGen's core philosophy and evolves independently |
| **Agency Swarm** | [VRSEN/agency-swarm](https://github.com/VRSEN/agency-swarm) | 6K+ | Built on OpenAI Assistants API; clear inter-agent communication protocol; ideal for quickly assembling specialized agent teams |

### Lightweight & Minimal Frameworks

| Framework | GitHub | Key Feature |
|---|---|---|
| **smolagents** | [huggingface/smolagents](https://github.com/huggingface/smolagents) | ~1,000 lines; top choice for learning; Code Agent paradigm |
| **Lagent** | [InternLM/lagent](https://github.com/InternLM/lagent) | By Shanghai AI Lab; streaming output; AgentLego visual extension |
| **Ell** | [MadcowD/ell](https://github.com/MadcowD/ell) | Treats prompts as functions; version control; visual tracing |
| **Upsonic** | [upsonic/upsonic](https://github.com/upsonic/upsonic) | Reliability-first; built-in MCP support; minimizes hallucinations |
| **nanobot** | [HKUDS/nanobot](https://github.com/HKUDS/nanobot) | ~4,000 lines of Python; 9+ message channels; best codebase for learning agent internals |

### Enterprise Frameworks

| Framework | GitHub | Description |
|---|---|---|
| **Semantic Kernel** | [microsoft/semantic-kernel](https://github.com/microsoft/semantic-kernel) | By Microsoft; C# / Python / Java; top choice for enterprise .NET; Azure OpenAI deep integration; Planner mode; powers the Copilot product family |
| **LlamaIndex** | [run-llama/llama_index](https://github.com/run-llama/llama_index) | Best for RAG and data-intensive agents; 70+ data connectors; all major vector DB support; LlamaCloud hosted platform |
| **Strands Agents** | [strands-agents/sdk-python](https://github.com/strands-agents/sdk-python) | By AWS; model-agnostic design; optional deep AWS integration (Lambda, CloudWatch, Infrastructure Security Scanning) |
| **Dify** | [langgenius/dify](https://github.com/langgenius/dify) | 129K+ stars; low-code LLM app platform; visual Pipeline builder; RAG + Agent + workflow in one; fastest path from prototype to production |
| **n8n** | [n8n-io/n8n](https://github.com/n8n-io/n8n) | 150K+ stars; 400+ integrations; AI-native workflows; works as both MCP client and MCP server; self-hosted + fair-code license |
| **Langflow** | [langflow-ai/langflow](https://github.com/langflow-ai/langflow) | Drag-and-drop RAG + Agent workflow designer; LangChain-based; one-click API publish |
| **Flowise** | [FlowiseAI/Flowise](https://github.com/FlowiseAI/Flowise) | 42K+ stars; visual agent builder; **acquired by Workday in August 2025**; open source portion still maintained; multi-agent orchestration, RAG pipeline, debug and evaluation end-to-end |
| **Pathway** | [pathwaycom/pathway](https://github.com/pathwaycom/pathway) | 50K+ stars; **real-time data + AI Agent fusion** platform; LLM apps continuously updated with live data streams; Kafka, REST API, filesystem data sources; ideal for agents that need real-time knowledge |

---

## 🦞 Personal AI Agents

Embed agents inside the messaging apps you already use and control real-world operations through natural language. The fastest-growing Agent subcategory in 2026.

| Project | GitHub | Stars | Description |
|---|---|---|---|
| ⭐ **OpenClaw** | [openclaw/openclaw](https://github.com/openclaw/openclaw) | 247K+ | **Hottest open source agent of 2026.** 9K → 210K+ stars in 60 days; TypeScript; local-first, self-hosted; WhatsApp / Telegram / Discord and more as UI; three-layer capability extension via Skills / Plugins / MCP; 13,729 community Skills on ClawHub. See [Awesome-OpenClaw](https://github.com/EthanYolo01/Awesome-OpenClaw) |
| **Open Interpreter** | [OpenInterpreter/open-interpreter](https://github.com/OpenInterpreter/open-interpreter) | 60K+ | Lets LLMs execute code locally; can control filesystem, browser, run any program; terminal UI; `01 Project` extends into an AI device ecosystem |
| **Letta (formerly MemGPT)** | [letta-ai/letta](https://github.com/letta-ai/letta) | 15K+ | Stateful agent platform; persistent memory is the core differentiator; learns across sessions; `Conversations` feature supports multiple concurrent experiences sharing memory; the benchmark for LLM agent memory systems |
| **Taxy.ai** | [TaxyAI/browser-extension](https://github.com/TaxyAI/browser-extension) | 2K+ | Personal agent as a browser extension; natural language control over browser operations |

---

## 💻 Code Agents

Specialized agents that truly understand, write, modify, and debug code. The most fiercely competitive area in 2026.

### Commercial Code Agents (Closed Source)

| Agent | Description | Benchmark |
|---|---|---|
| **Claude Code** | Anthropic official CLI; terminal-native; Agent Teams multi-agent collaboration | SWE-bench Verified **80.9%** (industry highest) |
| **Codex CLI** | OpenAI terminal agent; multi-model support | SWE-bench industry-leading |
| **Devin 2.0** | Cognition Labs; fully autonomous; sandboxed cloud environment; Interactive Planning | Industry's first commercial code agent |
| **GitHub Copilot Workspace** | Issue → PR full pipeline; Copilot Agent Mode in VS Code | Deep GitHub integration |

### Open Source Code Agents

| Project | GitHub | Stars | Description |
|---|---|---|---|
| ⭐ **OpenHands (formerly OpenDevin)** | [All-Hands-AI/OpenHands](https://github.com/All-Hands-AI/OpenHands) | 61K+ | Most active open source autonomous software engineering agent. Sandboxed execution; any LLM; GitHub Issue → PR full automation; containerized isolation for safety |
| ⭐ **Aider** | [paul-gauthier/aider](https://github.com/paul-gauthier/aider) | 33K+ | Terminal code editing agent; Git-native (auto-commits every change); any LLM; whole-codebase context awareness; Architect + Editor dual mode |
| **Cline** | [cline/cline](https://github.com/cline/cline) | 35K+ | VS Code extension; full terminal + browser access; human-in-the-loop approval per action; native MCP support; any LLM |
| **SWE-agent** | [princeton-nlp/SWE-agent](https://github.com/princeton-nlp/SWE-agent) | 15K+ | Princeton; Agent-Computer Interface (ACI) design philosophy; source of the SWE-bench dataset; top choice for academic research |
| **Roo-Code** | [RooVetGit/Roo-Code](https://github.com/RooVetGit/Roo-Code) | 25K+ | Cline fork; structured modes (Architect/Code/Ask/Debug); fewer hallucinations; stricter context control |
| **Continue.dev** | [continuedev/continue](https://github.com/continuedev/continue) | 25K+ | VS Code + JetBrains dual extension; open source AI coding assistant; local and cloud models; Tab autocomplete + chat + edit in one |
| **Agentless** | [OpenAutoCoder/Agentless](https://github.com/OpenAutoCoder/Agentless) | 3K+ | Framework-free approach to code repair; no complex agent infrastructure; high SWE-bench score; demonstration of clean minimalist implementation |

### Code Security Review Agents

| Project | Description |
|---|---|
| **CodeRabbit** | AI PR review; inline suggestions; security vulnerability detection; natural language summaries |
| **Ellipsis** | AI PR reviewer; context-aware; auto-describe, review, improve PRs |
| **Greptile** | AI code review with whole-codebase context; enterprise-grade context engine |

---

## 🌐 Browser & Computer Control Agents

Giving AI the ability to "see the screen, move the mouse, type on the keyboard" — Computer Use is one of the most important capability expansions for agents in 2025–2026.

### Commercial Products

| Agent | Description |
|---|---|
| **Claude Computer Use** | Anthropic's desktop/browser control; screenshot-driven; beta stage |
| **OpenAI Operator** | ChatGPT autonomous web agent; human-in-the-loop checkpoints; CUA (Computer Use Architecture) |
| **Microsoft Fara** | 7B-parameter model specialized for PC automation; GUI operations via Windows Copilot |
| **Browser Operator (Dia)** | Autonomous digital employee; acquired by Meta |

### Open Source Frameworks & Tools

| Project | GitHub | Stars | Description |
|---|---|---|---|
| ⭐ **Playwright MCP** | [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) | 15K+ | Most widely used browser agent tool; connects to any agent framework via MCP; full browser control |
| **Browser Use** | [browser-use/browser-use](https://github.com/browser-use/browser-use) | 60K+ | Advanced browser automation; vision-driven (GPT-4V); no coded selectors; direct DOM and visual element manipulation |
| **Browserbase** | [browserbase/stagehand](https://github.com/browserbase/stagehand) | 10K+ | Stagehand: AI-first browser automation framework; cloud headless browser infrastructure; enterprise-grade reliability |
| **UI-TARS** | [bytedance/UI-TARS](https://github.com/bytedance/ui-tars) | 12K+ | By ByteDance; GUI agent foundation model; VLM-driven computer control; topped GitHub Trending in February 2026 |
| **Agent S2 (Simular)** | [simular-ai/Agent-S](https://github.com/simular-ai/Agent-S) | 3K+ | OSWorld 50-step SOTA (34.5%); mixture-of-expert-components architecture; excellent long-action-sequence stability |
| **Skyvern** | [Skyvern-AI/skyvern](https://github.com/Skyvern-AI/skyvern) | 12K+ | Reliable web automation API; CAPTCHA handling; production-grade stability |
| **Firecrawl** | [mendableai/firecrawl](https://github.com/mendableai/firecrawl) | 85K+ | Converts any webpage to LLM-friendly Markdown; noise removal; crawler + MCP dual mode |

### Application Testing Agents

| Agent | Description |
|---|---|
| **[agent-qa](https://vostride.com)** | Natural-language web, Android, and iOS testing for developers, with persistent memory, validated self-improvement, and CLI/MCP workflows. [Source](https://github.com/vostride/agent-qa) · FSL-1.1-ALv2. |

---

## 🔬 Research & Deep Exploration Agents

Agents designed specifically for research, information retrieval, and knowledge synthesis.

| Project | GitHub | Stars | Description |
|---|---|---|---|
| ⭐ **GPT Researcher** | [assafelovic/gpt-researcher](https://github.com/assafelovic/gpt-researcher) | 21K+ | Parallelized deep research; main agent decomposes the problem → multiple executor agents search in parallel → synthesized report; fast and low-bias |
| **LangManus** | [Darwin-lfl/langmanus](https://github.com/Darwin-lfl/langmanus) | 31K+ | ByteDance open source; open source SuperAgent; research + coding + creation combined; agent toolkit + sandbox execution |
| **Manus** | Commercial | — | ByteDance's commercial agent product; autonomous digital employee; tasks from minutes to hours |
| **Perplexica** | [ItzCrazyKns/Perplexica](https://github.com/ItzCrazyKns/Perplexica) | 33K+ | Open source AI search engine alternative; deep research mode; RAG + search fusion |
| **Storm (Stanford)** | [stanford-oval/storm](https://github.com/stanford-oval/storm) | 18K+ | Stanford; collects information from the web to generate Wikipedia-like long articles; multi-perspective Q&A; NAACL 2024 Best Paper |

---

## 🧠 Agent Memory Systems

Memory is the key capability that transforms agents from "single-turn Q&A tools" into "genuine assistants." This area experienced explosive growth in 2025–2026.

### Memory Frameworks & Tools

| Project | GitHub | Description |
|---|---|---|
| ⭐ **MemOS** | [MemTensor/MemOS](https://github.com/MemTensor/MemOS) | **Memory Operating System.** Elevates memory to a first-class citizen: MemCube (unified memory object) encapsulates parametric memory, activation memory, and external storage; cross-task skill reuse and memory evolution. Has an OpenClaw plugin (reduces token usage by 72%) |
| ⭐ **mem0** | [mem0ai/mem0](https://github.com/mem0ai/mem0) | 35K+ stars. Self-improving personalized memory layer; automatically extracts and updates user preferences; works across all major agent frameworks; top scores on LongMemEval leaderboard |
| **Letta (formerly MemGPT)** | [letta-ai/letta](https://github.com/letta-ai/letta) | Stateful agent development environment; self-managed context compression; Agent Development Environment (ADE) |
| **Graphiti (Zep)** | [getzep/graphiti](https://github.com/getzep/graphiti) | Temporal knowledge graph; memory has a time dimension; ideal for long-horizon agents that need to track "when things happened" |
| **ReMe** | [agentscope-ai/ReMe](https://github.com/agentscope-ai/ReMe) | By Alibaba AgentScope team; complete toolkit for memory extraction, refinement, and retrieval; multi-backend vector storage |
| **Cognee** | [topoteretes/cognee](https://github.com/topoteretes/cognee) | Knowledge graph + vector search fusion; trustworthy memory layer for agents; structured knowledge management |
| **Supermemory** | [supermemoryai/supermemory](https://github.com/supermemoryai/supermemory) | Managed external memory service; semantic search; shared memory across multiple agent instances; open source + cloud |

### Memory-Related Academic Resources

| Resource | Description |
|---|---|
| [Memory in the Age of AI Agents (Survey)](https://arxiv.org/abs/2512.13564) | Most comprehensive agent memory survey to date; unified taxonomy; HuggingFace Daily #1 |
| [Awesome-Agent-Memory](https://github.com/TeleAI-UAGI/Awesome-Agent-Memory) | Curated paper and resource list focused on memory systems; continuously updated |
| [Agent-Memory-Paper-List](https://github.com/Shichun-Liu/Agent-Memory-Paper-List) | Paper collection organized by memory type |
| [MemoryAgentBench (ICLR 2026)](https://github.com/HUST-AI-HYZ/MemoryAgentBench) | Benchmark evaluating LLM agent memory through incremental multi-turn interactions |

---

## 🛠️ Tools & Integrations

### Tool-Calling Frameworks

| Tool | GitHub | Description |
|---|---|---|
| ⭐ **Composio** | [ComposioHQ/composio](https://github.com/ComposioHQ/composio) | **1,000+ tools in one integration.** Unified auth management; tool search; context management; sandbox workbench. 27K+ stars; compatible with all major agent frameworks and MCP |
| **Toolhouse** | [toolhouseai](https://github.com/toolhouseai) | Cloud tool storage and execution; equip agents with tools in one line; built-in tool marketplace |
| **AgentRPC** | [agentrpc/agentrpc](https://github.com/agentrpc/agentrpc) | Call any function across languages and network boundaries; lets agents use tools written in any language |

### Code Execution Sandboxes

| Tool | GitHub | Description |
|---|---|---|
| ⭐ **E2B** | [e2b-dev/e2b](https://github.com/e2b-dev/e2b) | Secure code execution sandbox designed for AI agents; millisecond startup; Python / JS / any language; cloud-hosted |
| **Daytona** | [daytonaio/daytona](https://github.com/daytonaio/daytona) | Secure AI-generated code runtime; DAST security scanning; Kubernetes-native |
| **Modal** | [modal-labs/modal-client](https://github.com/modal-labs/modal-client) | Serverless GPU compute; elastic execution environment for agent tasks |

### Local Model Running

Local model running tools are essential for agent local deployment — fully solving privacy, cost, and offline requirements:

| Tool | GitHub | Stars | Description |
|---|---|---|---|
| ⭐ **Ollama** | [ollama/ollama](https://github.com/ollama/ollama) | 130K+ | **Top choice for running local LLMs.** One-line command to download and run Llama, Qwen, Gemma, DeepSeek and more; macOS/Windows/Linux support; REST API compatible with OpenAI interface so all agent frameworks connect directly; privacy-first, zero data egress |
| **LM Studio** | [lmstudio-ai/lmstudio.js](https://github.com/lmstudio-ai/lmstudio.js) | 5K+ | GUI tool for running local models; GGUF format; built-in OpenAI-compatible server; ideal for users not comfortable with the command line |
| **Jan** | [janhq/jan](https://github.com/janhq/jan) | 28K+ | Fully offline AI assistant desktop app; local model + remote API dual mode; 100% private |

### Agent Communication Protocols

| Protocol | Description |
|---|---|
| **MCP (Model Context Protocol)** | Initiated by Anthropic, now a Linux Foundation neutral standard. Agent ↔ tool communication protocol. See [Awesome-MCP](https://github.com/EthanYolo01/Awesome-MCP) |
| **A2A (Agent-to-Agent)** | [a2aproject/A2A](https://github.com/a2aproject/A2A) — Google's open inter-agent communication protocol; CrewAI already supports it; LangGraph adapting |
| **ACP (Agent Communication Protocol)** | [agentcommunicationprotocol.dev](https://agentcommunicationprotocol.dev) — Broader agent interoperability protocol |

---

## 📊 Observability, Evaluation & Benchmarks

**Once agents reach production, "is it working well?" matters more than "does it run?"** This area moved from research to engineering necessity in 2025–2026.

### Observability & Tracing

| Tool | Description |
|---|---|
| ⭐ **LangSmith** | LangChain's official observability platform; traces every LLM call; A/B testing; evaluation suite; production monitoring and alerting |
| ⭐ **Langfuse** | [langfuse/langfuse](https://github.com/langfuse/langfuse) — Open source LLM observability; framework-agnostic; self-hosted option; tracing + evaluation + prompt management in one |
| **AgentOps** | Agent-specialized tracing platform; session replay; cost analysis; error categorization |
| **Weave (W&B)** | Weights & Biases LLM evaluation and tracing; experiment management |
| **Helicone** | LLM request proxy + observability; caching; rate limiting; cost tracking |
| **Arize Phoenix** | [Arize-ai/phoenix](https://github.com/Arize-ai/phoenix) — Open source AI observability; RAG evaluation; embedding visualization |

### Code Agent Benchmarks

| Benchmark | Description | 2026 SOTA |
|---|---|---|
| **SWE-bench Verified** | Tests code repair on real GitHub issues; 500 human-verified problems | Claude Code: **80.9%** |
| **SWE-bench Lite** | Condensed version (300 problems); faster evaluation | Claude Code / OpenHands leading |
| **LiveCodeBench** | Continuously updated competitive programming; anti-data-contamination | Frontier models competing |
| **HumanEval / MBPP** | Classic code generation benchmarks; largely superseded by SWE-bench | Near saturation |

### Computer Control Benchmarks

| Benchmark | Description | 2026 SOTA |
|---|---|---|
| **OSWorld** | Desktop GUI operation environment; 15-step and 50-step tasks | Agent S2 (Simular): 34.5% (50-step) |
| **WebArena** | Web interaction task simulator | Multiple frameworks competing |
| **GAIA** | General AI agent benchmark; multi-step real-world tasks | Various agent frameworks competing |

### Agent Evaluation Frameworks

| Tool | Description |
|---|---|
| **AgentBench** | [THUDM/AgentBench](https://github.com/THUDM/AgentBench) — Unified agent evaluation across 8 real-world environments |
| **PromptFoo** | [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo) — LLM application testing framework; red-teaming; automated evaluation |
| **Maxim AI** | Online evaluation + tracing + human review workflows; production agent quality assurance |

---

## 🔒 Agent Security

Agents have broad tool-calling and system access. Security cannot be an afterthought.

### Main Threats

| Threat | Description | Mitigation |
|---|---|---|
| **Prompt Injection** | Malicious content in tool responses hijacks agent behavior | Output sanitization; tool return validation; agent constitution constraints |
| **Tool Misuse** | Agent calls tools beyond necessary scope | Least privilege; tool whitelist; human-in-the-loop |
| **Data Exfiltration** | Agent accesses and leaks sensitive information | Access controls; data masking; audit logs |
| **Goal Drift** | Agent drifts from original goal during long-horizon tasks | Periodic checkpoints; goal alignment verification; human oversight |
| **Uncontrolled Actions** | Agent executes irreversible high-risk operations | Write operations require approval; sandbox execution; rollback mechanisms |
| **Supply Chain Attacks** | Malicious agent tools or MCP servers | Tool source verification; mcp-scan; code review |

### Security Tools

| Tool | Description |
|---|---|
| **mcp-scan** | [invariantlabs-ai/mcp-scan](https://github.com/invariantlabs-ai/mcp-scan) — MCP tool security scanner; detects prompt injection and tool poisoning |
| **Guardrails AI** | [guardrails-ai/guardrails](https://github.com/guardrails-ai/guardrails) — LLM input/output guardrails; format validation; content filtering |
| **NeMo Guardrails** | [NVIDIA/NeMo-Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) — By NVIDIA; conversational AI safety rails; topic restrictions; fact checking |
| **BoostSecurity** | Prevents AI agents from introducing vulnerable dependency packages; CI/CD integration |
| **Rebuff** | [woop/rebuff](https://github.com/woop/rebuff) — Prompt injection defense framework; heuristic + LLM dual detection |
| **LakeraGuard** | Enterprise AI security API; real-time prompt injection and data exfiltration detection |

### Security Best Practices

1. **Least privilege** — agents should only have the minimum permissions needed for the current task
2. **Human-in-the-Loop (HITL)** — write operations, irreversible operations, high-risk decisions must have human approval
3. **Sandboxed execution** — code execution happens in isolated environments (E2B, Docker)
4. **Audit logs** — log all tool calls for post-incident review and accountability
5. **Input/output sanitization** — treat tool return values as untrusted input; always validate and sanitize
6. **Periodic checkpoints** — periodically verify the agent is still on the correct path during long-horizon tasks

**Further reading:**
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [OWASP Agentic Security Initiative](https://genai.owasp.org/initiatives/agentic-security-initiative/)
- [MITRE ATLAS — AI Attack Knowledge Base](https://atlas.mitre.org)

---

## 🤖 Embodied Agents & Robotics

Extending agent capabilities into the physical world — robots, home assistants, industrial automation.

| Project | GitHub | Stars | Description |
|---|---|---|---|
| **LeRobot (HuggingFace)** | [huggingface/lerobot](https://github.com/huggingface/lerobot) | 38K+ | End-to-end deep learning for real robots; teleoperation datasets; ready-to-use ML toolchain |
| **ROS 2** | [ros2/ros2](https://github.com/ros2/ros2) | — | Robot Operating System 2; de facto standard for robot software; LLM integration plugin ecosystem growing |
| **Genesis** | [Genesis-Embodied-AI/Genesis](https://github.com/Genesis-Embodied-AI/Genesis) | — | Physics simulation platform for embodied AI and robotics; 43M polygon/second rendering |
| **π0 (Physical Intelligence)** | Commercial | — | Universal robot foundation model; cross-robot-type skill transfer |

---

## 📖 Tutorials, Blogs & Articles

### Official Documentation & Getting Started

- [LangChain Agent Docs](https://python.langchain.com/docs/how_to/#agents) — Tool calling, ReAct, custom agents: complete guide
- [LangGraph Quickstart](https://langchain-ai.github.io/langgraph/tutorials/introduction/) — Build a state machine agent from scratch
- [OpenAI Agents SDK Docs](https://openai.github.io/openai-agents-python/) — Multi-Agent, Handoffs, Guardrails: detailed guide
- [Google ADK Docs](https://google.github.io/adk-docs/) — Agent development toolkit powered by Gemini
- [AutoGen Docs](https://microsoft.github.io/autogen/) — Multi-agent conversation framework complete guide
- [HuggingFace Agent Course](https://github.com/huggingface/agents-course) ⭐ — **Free open source agent dev course**; covers smolagents, LlamaIndex, LangGraph; certificate on completion

### In-Depth Technical Articles

- [2026 AI Agent Framework Decision Guide](https://dev.to/linou518/the-2026-ai-agent-framework-decision-guide-langgraph-vs-crewai-vs-pydantic-ai-b2h) — LangGraph vs CrewAI vs Pydantic AI head-to-head
- [10 Best AI Agent Frameworks Compared (2026)](https://arsum.com/blog/posts/ai-agent-frameworks/) — Deep framework analysis with decision matrix
- [Langfuse: Complete Open Source Agent Framework Comparison](https://langfuse.com/blog/2025-03-19-ai-agent-comparison) — Comprehensive analysis of 12 frameworks
- [OpenAI: A Practical Guide to Building Agents](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf) — Architecture patterns, guardrail design, production considerations
- [Letta: The AI Agent Tech Stack](https://www.letta.com/blog/ai-agents-stack) — Layered breakdown of the 2025 agent tech stack
- [GAIA Benchmark: How Far to General AI Agents?](https://arxiv.org/abs/2311.12983) — Quantified gap between agent capability and human performance
- [LangChain: State of Agent Engineering (2026)](https://www.langchain.com/state-of-agent-engineering) — 1,300+ practitioner survey; 57% already deploying agents in production; 32% cite quality as biggest barrier; 89% have implemented observability
- [Firecrawl: Best Open Source Agent Frameworks (2026)](https://www.firecrawl.dev/blog/best-open-source-agent-frameworks) — LangGraph 34.5M monthly downloads, Dify 129K stars; 10 production principles from Anthropic/OpenAI/McKinsey
- [ByteByteGo: Top AI GitHub Repositories in 2026](https://blog.bytebytego.com/p/top-ai-github-repositories-in-2026) — Systematic breakdown of OpenClaw, n8n, Langflow, Dify and more
- [Asher Technologies: Every Agent Framework, Platform and Protocol for 2026](https://ashertech.ca/blog/agentic-ai-tools-guide-2026) — Most comprehensive ecosystem overview; includes Microsoft Agent Framework merger, $7.8B market size data

### Learning Paths

**Beginners (understanding what AI agents are):**
1. Read the **Core Concepts Quick Reference** section above to understand the fundamentals
2. Install [Claude Desktop](https://claude.ai/download) to experience Agent + MCP tool calling
3. Write your first agent with [smolagents](https://github.com/huggingface/smolagents) (~50 lines of code)
4. Follow [HuggingFace Agent Course](https://github.com/huggingface/agents-course) for a structured curriculum

**Developers (building production agents):**
1. Use **CrewAI** first to quickly validate business ideas (lowest onboarding cost)
2. Migrate to **LangGraph** when you need precise control (graph state machine + checkpointing)
3. TypeScript stack: choose **Mastra** or **VoltAgent**
4. Integrate **LangSmith** or **Langfuse** tracing from day one — don't wait until something breaks

---

## 📚 Papers & Academic Resources

### Foundational Papers

| Paper | Year | Significance |
|---|---|---|
| [ReAct: Synergizing Reasoning and Acting](https://arxiv.org/abs/2210.03629) | 2022 | Foundational work: Thought-Action-Observation paradigm; theoretical basis for mainstream agent loops |
| [Chain-of-Thought Prompting](https://arxiv.org/abs/2201.11903) | 2022 | Foundation for reasoning capability; CoT is a prerequisite for all advanced agent reasoning |
| [Toolformer: Language Models Can Teach Themselves to Use Tools](https://arxiv.org/abs/2302.04761) | 2023 | Self-supervised tool use learning; lays the research foundation for tool calling |
| [HuggingGPT: Solving AI Tasks with ChatGPT](https://arxiv.org/abs/2303.04671) | 2023 | Multi-model collaborative orchestration; LLM as task planner paradigm |
| [Voyager: An Open-Ended Embodied Agent with LLMs](https://arxiv.org/abs/2305.16291) | 2023 | Lifelong learning agent in Minecraft; continuously expanding skill library |

### Recent Important Papers (2025–2026)

| Paper | Year | Description |
|---|---|---|
| [Agentic Reasoning for Large Language Models](https://arxiv.org/abs/2601.12538) | 2026 | Comprehensive survey on agent reasoning; classification framework; evaluation system |
| [Memory in the Age of AI Agents: A Survey](https://arxiv.org/abs/2512.13564) | 2025/2026 | Most comprehensive agent memory systems survey; HuggingFace Daily #1 |
| [SWE-bench Verified](https://arxiv.org/abs/2310.06770) | 2023/ongoing | Standard code agent benchmark; quantitative software engineering evaluation |
| [GAIA: A Benchmark for General AI Assistants](https://arxiv.org/abs/2311.12983) | 2023/ongoing | General agent capability evaluation; tests multi-step real-world tasks |
| [MemoryAgentBench (ICLR 2026)](https://arxiv.org/abs/2507.05257) | 2025 | Agent memory evaluation through incremental multi-turn interactions |
| [A Survey on LLM-based Autonomous Agents](https://arxiv.org/abs/2308.11432) | 2023 | Survey on autonomous agent systems; three-dimensional analysis of building, applying, evaluating |

### Paper & Resource Collections

| Collection | Description |
|---|---|
| [awesome-ai-agent-papers (VoltAgent)](https://github.com/VoltAgent/awesome-ai-agent-papers) | Curated 2026 agent papers; weekly updates from arXiv; multi-agent, memory, evaluation, security |
| [Awesome-Agentic-Reasoning](https://github.com/weitianxin/Awesome-Agentic-Reasoning) | Agent reasoning resources based on ICLR 2026 papers |
| [Awesome-Agent-Memory](https://github.com/TeleAI-UAGI/Awesome-Agent-Memory) | Papers and tools focused on agent memory systems |

---

## 🗺️ Related Awesome Lists

| List | Scope |
|---|---|
| [caramaschiHG/awesome-ai-agents-2026](https://github.com/caramaschiHG/awesome-ai-agents-2026) | Most comprehensive 2026 agent list; 300+ resources, 20+ categories; monthly updates |
| [e2b-dev/awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents) | Classic list maintained by e2b; autonomous agents and SDKs |
| [kyrolabs/awesome-agents](https://github.com/kyrolabs/awesome-agents) | Framework and tool-oriented; frequently updated |
| [kaushikb11/awesome-llm-agents](https://github.com/kaushikb11/awesome-llm-agents) | Curated LLM frameworks and tools; updated 2026-03-15 |
| [slavakurilyak/awesome-ai-agents](https://github.com/slavakurilyak/awesome-ai-agents) | 300+ resources; sorted by stars |
| [EthanYolo01/Awesome-OpenClaw](https://github.com/EthanYolo01/Awesome-OpenClaw) | OpenClaw personal AI agent framework resources (sister list) |
| [EthanYolo01/Awesome-MCP](https://github.com/EthanYolo01/Awesome-MCP) | MCP protocol resource collection (sister list) |

---

## 🤝 Contributing

Contributions are welcome! This list prioritizes **verified links + opinionated curation** over exhaustive listing.

**Before submitting:**
1. Verify the link is real and working (visit it yourself)
2. Include a clear description (what, who, why it belongs here)
3. Check for duplicates first
4. Match the format of the existing section

**Maintainer contact:** kalayolo86@gmail.com

---

<div align="center">

**Found this useful?** Give it a ⭐ and share it with your team.
**Something missing or a dead link?** [Open an issue](https://github.com/EthanYolo01/Awesome-Agent/issues) or submit a PR.

*Last updated: March 2026 · Maintained with ❤️ by the community*

🌐 Language / 语言切换：**English** | [中文](README_CN.md)

</div>
