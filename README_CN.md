<div align="center">

# 🤖 Awesome Agent 中文资源大合集

**精选 AI Agent 优质资源 —— 框架、工具、记忆系统、基准测试、论文与学习资料**

*持续收集 · 人工验证 · 精选干货*

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-欢迎提交-brightgreen.svg?style=flat-square)](CONTRIBUTING.md)
[![License: CC0-1.0](https://img.shields.io/badge/许可证-CC0_1.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/publicdomain/zero/1.0/)
[![最近更新](https://img.shields.io/badge/最近更新-2026年3月-blue?style=flat-square)](https://github.com/EthanYolo01/Awesome-Agent/commits/main)
[![Stars](https://img.shields.io/github/stars/EthanYolo01/Awesome-Agent?style=flat-square)](https://github.com/EthanYolo01/Awesome-Agent/stargazers)

> **有观点的精选，不是无脑堆砌。**
> 每一条资源都经过人工审核和链接验证。我们告诉你每个资源*为什么*值得关注，以及*什么时候*该用它。

**AI Agent 现状（2026 年 3 月）：** 🗂️ GitHub 上 430 万+ AI 相关仓库 &nbsp;·&nbsp; 🤖 LLM Agent 相关项目同比增长 178% &nbsp;·&nbsp; 🏭 68% 的生产 Agent 使用开源框架 &nbsp;·&nbsp; 🌐 MCP + A2A 成为 Agent 互操作标准

---

🌐 语言切换 / Language：**中文** | [English](README.md)

</div>

---

## 📋 目录

- [🏁 什么是 AI Agent？](#-什么是-ai-agent)
- [⏳ 发展历程](#-发展历程)
- [🧠 核心概念速查](#-核心概念速查)
- [🏗️ Agent 框架全景](#️-agent-框架全景)
  - [通用 Agent 框架](#通用-agent-框架)
  - [多 Agent 协作框架](#多-agent-协作框架)
  - [轻量级与极简框架](#轻量级与极简框架)
  - [企业级框架](#企业级框架)
- [🦞 个人 AI Agent](#-个人-ai-agent)
- [💻 代码 Agent](#-代码-agent)
- [🌐 浏览器与计算机控制 Agent](#-浏览器与计算机控制-agent)
- [🔬 研究与深度探索 Agent](#-研究与深度探索-agent)
- [🧠 Agent 记忆系统](#-agent-记忆系统)
- [🛠️ 工具与集成](#️-工具与集成)
  - [工具调用框架](#工具调用框架)
  - [代码执行沙盒](#代码执行沙盒)
  - [本地模型运行](#本地模型运行)
  - [Agent 通信协议](#agent-通信协议)
- [📊 可观测性、评估与基准测试](#-可观测性评估与基准测试)
- [🔒 Agent 安全](#-agent-安全)
- [🤖 具身 Agent 与机器人](#-具身-agent-与机器人)
- [📖 教程、博客与文章](#-教程博客与文章)
- [📚 论文与学术资源](#-论文与学术资源)
- [🗺️ 相关 Awesome 列表](#️-相关-awesome-列表)

---

## 🏁 什么是 AI Agent？

**AI Agent（智能体）** 是能够感知环境、自主规划、调用工具并执行多步骤任务以达成目标的 AI 系统。与单次问答的 LLM 不同，Agent 可以主动决策、使用工具、记住上下文，并在没有人类逐步指导的情况下完成复杂任务。

**一句话理解：** 普通 LLM = 一次性回答一个问题；Agent = 理解目标 → 制定计划 → 调用工具 → 执行操作 → 验证结果 → 循环直到完成。

**Agent 与普通 LLM 调用的核心区别：**

| 维度 | 普通 LLM | AI Agent |
|---|---|---|
| **任务范围** | 单轮问答 | 多步骤、长时程任务 |
| **工具调用** | 无 | 可调用搜索、代码执行、API、浏览器等 |
| **记忆** | 仅当前上下文窗口 | 跨会话持久记忆 |
| **规划** | 无 | 可分解任务、制定执行计划 |
| **自主性** | 被动响应 | 主动决策和行动 |
| **错误恢复** | 无 | 可检测错误并重试 |

**三种典型 Agent 模式：**

```
ReAct 模式（最常见）:
  思考(Thought) → 行动(Action) → 观察(Observation) → 循环

规划-执行模式:
  制定计划 → 逐步执行 → 验证结果

多 Agent 协作:
  协调者 → 分派给专业子 Agent → 汇总结果
```

---

## ⏳ 发展历程

```
2022年  ──  ReAct 论文（Yao et al.）提出"推理 + 行动"范式
            Chain-of-Thought 奠定 Agent 推理基础
            WebGPT 展示 LLM + 搜索工具的可能性

2023年初 ── AutoGPT 爆红（100K+ stars），让"自主 Agent"进入公众视野
            BabyAGI：任务驱动的自主 Agent 原型
            HuggingGPT / TaskMatrix：多模型协作思路提出
            LangChain 成为 Agent 框架事实标准

2023年中 ── MetaGPT：将多 Agent 模拟成软件公司团队
            AutoGen（微软）：对话驱动的多 Agent 框架
            Voyager：在 Minecraft 中持续学习的具身 Agent

2024年  ──  OpenDevin（现 OpenHands）：开源自主软件工程 Agent
            SWE-bench 成为代码 Agent 标准基准
            Devin（Cognition）：商业代码 Agent 发布，引发行业关注
            LangGraph 发布：图状态机为复杂工作流提供更精确控制
            Claude Computer Use：Anthropic 发布计算机控制能力（beta）
            MCP 协议发布：Agent 工具调用标准化

2025年  ──  OpenAI Agents SDK 发布：多 Agent 编排的官方框架
            Google ADK（Agent Development Kit）发布
            Mastra：TypeScript Agent 框架崛起
            Pydantic AI：类型安全 Python Agent 框架
            Agent 基准测试成熟：GAIA、OSWorld、SWE-bench Verified
            A2A 协议（Google）：Agent 间通信标准化尝试
            MCP 捐献 Linux 基金会，成为中立开放标准

2026年初 ── Claude Code 达到 SWE-bench Verified 80.9%，代码 Agent 能力突破
            Gemini CLI + 原生 MCP 支持
            OpenClaw 爆红（60 天从 9K 到 210K+ stars）
            VoltAgent、Mastra 等 TypeScript 框架快速崛起
            MemOS、Letta 等记忆操作系统成为新热点
            多 Agent 协作成为生产主流（Gartner：2027 年 1/3 部署将是多 Agent）
```

---

## 🧠 核心概念速查

### Agent 的四大能力模块

| 模块 | 说明 | 典型实现 |
|---|---|---|
| **感知（Perception）** | 接收输入：文本、图像、音频、工具返回值、环境状态 | 多模态模型、视觉理解 |
| **规划（Planning）** | 分解任务、制定步骤、处理不确定性 | ReAct、CoT、Tree-of-Thought、MCTS |
| **记忆（Memory）** | 跨步骤、跨会话保留信息 | 向量数据库、知识图谱、上下文压缩 |
| **行动（Action）** | 调用工具、生成代码、控制系统、与其他 Agent 通信 | 工具调用、代码执行、MCP、API |

### 记忆类型

| 类型 | 说明 | 类比 |
|---|---|---|
| **工作记忆（Working Memory）** | 当前上下文窗口内的信息 | 人类短期记忆 |
| **情节记忆（Episodic Memory）** | 历史对话和事件日志 | 人类的具体经历 |
| **语义记忆（Semantic Memory）** | 提炼出的知识和事实 | 人类的知识体系 |
| **过程记忆（Procedural Memory）** | 如何执行任务的方法和技能 | 肌肉记忆 |
| **参数记忆（Parametric Memory）** | 编码在模型权重中的知识 | 本能和直觉 |

### 常见 Agent 架构模式

**ReAct（推理 + 行动）** — 最广泛采用的范式：
```
User: "研究 2026 年 AI Agent 市场规模"
Agent 思考: 需要搜索最新数据
Agent 行动: search("2026 AI agent market size")
Agent 观察: [搜索结果]
Agent 思考: 找到了数据，需要进一步分析
Agent 行动: analyze(data)
...最终回答
```

**规划者-执行者（Planner-Executor）** — 先规划再执行，适合确定性任务。

**反思（Reflexion）** — Agent 对自己的输出进行自我批评和改进，适合需要高质量输出的任务。

**多 Agent 协作** — 专业化分工：一个 Agent 搜索，一个分析，一个撰写，一个审核。

---

## 🏗️ Agent 框架全景

### 框架选型决策树

```
你的需求是...
├── 快速原型验证？
│   └── CrewAI 或 OpenAI Agents SDK
├── 复杂状态机 + 长期维护？
│   └── LangGraph
├── 类型安全 + 高稳定性？
│   └── Pydantic AI
├── TypeScript 优先？
│   └── Mastra 或 VoltAgent
├── 企业 .NET/Azure 生态？
│   └── Microsoft Agent Framework（AutoGen v0.4+）
├── RAG 密集型应用？
│   └── LlamaIndex Agents
├── 最小化依赖 + 教学用途？
│   └── smolagents
└── 全定制 + 数据主权？
    └── 考虑从头构建或 OpenClaw
```

### 通用 Agent 框架

| 框架 | 语言 | GitHub | Stars | 说明 |
|---|---|---|---|---|
| ⭐ **LangGraph** | Python | [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) | 13K+ | **复杂工作流首选**。图状态机架构，节点 + 边定义执行流；内置检查点、断点续行、Human-in-the-loop；LangSmith 深度集成可观测性。比简单链多 30-40% 控制力，代价是更高学习曲线 |
| ⭐ **OpenAI Agents SDK** | Python | [openai/openai-agents-python](https://github.com/openai/openai-agents-python) | 6K+ | OpenAI 官方多 Agent 编排框架。Agents、Handoffs、Guardrails 三大核心原语；内置追踪；若你的技术栈以 OpenAI 为中心，这是最低摩擦的选择 |
| ⭐ **Google ADK** | Python / Java | [google/adk-python](https://github.com/google/adk-python) | 8K+ | Google 官方 Agent 开发工具包。多 Agent 编排，内置 Gemini 集成；Vertex AI 原生部署；代码优先设计，工具定义简洁 |
| **Pydantic AI** | Python | [pydantic/pydantic-ai](https://github.com/pydantic/pydantic-ai) | 10K+ | 来自 Pydantic 团队。类型安全是核心卖点——工具输入输出都有完整类型验证；依赖注入；模型无关。生产代码质量高，减少运行时错误 |
| **Mastra** | TypeScript | [mastra-ai/mastra](https://github.com/mastra-ai/mastra) | 20K+ | TypeScript 开发者的最佳选择。内置工具库、记忆、RAG、工作流、可观测性；官方集成 MCP；设计理念：约定优于配置 |
| **VoltAgent** | TypeScript | [VoltAgent/voltagent](https://github.com/voltagent/voltagent) | 3K+ | 开源 TypeScript Agent 框架，内置 LLM 可观测性；子 Agent 系统；MCP 客户端支持；适合全栈 Node.js 项目 |
| **Agno** | Python | [agno-agi/agno](https://github.com/agno-agi/agno) | 25K+ | 极速 Agent SDK（3.77μs Agent 实例化，业内最快）；支持 100+ LLM；内置记忆、知识库、工具、多 Agent 团队 |
| **AutoGPT** | Python | [Significant-Gravitas/AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) | 182K+ | **最早让「自主 Agent」进入公众视野的项目**。已从实验性 CLI 进化为完整 Agent 平台：CoPilot 助手、可视化工作流构建器、E2B 沙盒代码执行、MCP 服务器发现、Agent 市场；2026 年 3 月仍在活跃发布（v0.6.50） |
| **smolagents** | Python | [huggingface/smolagents](https://github.com/huggingface/smolagents) | 15K+ | HuggingFace 出品。极简设计，~1000 行核心代码，可一下午读完；Code Agent（直接生成 Python 代码执行）范式；模型无关；适合学习 Agent 原理或快速原型 |
| **Haystack** | Python | [deepset-ai/haystack](https://github.com/deepset-ai/haystack) | 18K+ | 面向 NLP Pipeline 和 RAG 场景；Pipeline 组件化设计；生产检索增强应用的成熟选择 |

### 多 Agent 协作框架

| 框架 | GitHub | Stars | 说明 |
|---|---|---|---|
| ⭐ **CrewAI** | [crewAIInc/crewAI](https://github.com/crewAIInc/crewAI) | 46K+ | **多 Agent 框架中上手最快的**。角色扮演隐喻：每个 Agent 有 Role、Goal、Backstory；Team → Task → Agent 的直觉映射。适合内容生成、研究分析、客服分流等业务工作流。CrewAI AMP 企业版含 Salesforce / Gmail / Slack 触发器 |
| **Microsoft Agent Framework（AutoGen 继任者）** | [microsoft/autogen](https://github.com/microsoft/autogen) | 38K+ | 2025 年 10 月微软将 AutoGen 与 Semantic Kernel **合并**为统一的 Microsoft Agent Framework（GA 目标 Q1 2026）。AutoGen 现处于维护模式，仅接受 Bug 修复；新项目应使用 Microsoft Agent Framework + Azure AI Foundry 集成。Group Chat、Sequential Chat 等经典模式仍可用 |
| **MetaGPT** | [geekan/MetaGPT](https://github.com/geekan/MetaGPT) | 57K+ | 模拟软件公司团队：产品经理、架构师、程序员、测试人员各司其职。给一行需求，返回 PRD、设计文档、代码、CI 配置。软件工程 Pipeline 自动化的标杆项目 |
| **OpenAgents** | [OpenAgentsInc/openagents](https://github.com/OpenAgentsInc/openagents) | 1.7K+ | 原生支持 MCP + A2A 双协议；持久 Agent 网络；模块化扩展系统。目前唯一同时原生支持两大 Agent 互操作协议的框架 |
| **AG2** | [ag2ai/ag2](https://github.com/ag2ai/ag2) | 36K+ | AutoGen 原创团队的延续项目（社区分支）；保持 AutoGen 核心理念，独立演进 |
| **Agency Swarm** | [VRSEN/agency-swarm](https://github.com/VRSEN/agency-swarm) | 6K+ | 基于 OpenAI Assistants API 构建；Agent 间通信协议清晰；适合快速搭建专业化 Agent 团队 |

### 轻量级与极简框架

| 框架 | GitHub | 特点 |
|---|---|---|
| **smolagents** | [huggingface/smolagents](https://github.com/huggingface/smolagents) | ~1000 行，教学首选；Code Agent 范式 |
| **Lagent** | [InternLM/lagent](https://github.com/InternLM/lagent) | 上海 AI Lab 出品；流式输出；可视化 AgentLego 扩展 |
| **Ell** | [MadcowD/ell](https://github.com/MadcowD/ell) | 将 Prompt 当函数处理；版本控制；可视化追踪 |
| **Upsonic** | [upsonic/upsonic](https://github.com/upsonic/upsonic) | 可靠性优先；内置 MCP 支持；最小化幻觉 |
| **nanobot** | [HKUDS/nanobot](https://github.com/HKUDS/nanobot) | ~4000 行 Python；支持 MCP 和 9+ 消息频道；学习 Agent 内部原理的最佳代码库 |

### 企业级框架

| 框架 | GitHub | 说明 |
|---|---|---|
| **Semantic Kernel** | [microsoft/semantic-kernel](https://github.com/microsoft/semantic-kernel) | 微软出品；C# / Python / Java 三语言；企业 .NET 生态首选；Azure OpenAI 深度集成；Planner 模式；Copilot 系列产品底层 |
| **LlamaIndex** | [run-llama/llama_index](https://github.com/run-llama/llama_index) | RAG 和数据密集型 Agent 的最佳选择；70+ 数据连接器；所有主流向量数据库支持；LlamaCloud 托管平台 |
| **Strands Agents** | [strands-agents/sdk-python](https://github.com/strands-agents/sdk-python) | AWS 出品；模型无关设计；可选深度 AWS 集成（Lambda、CloudWatch、Infrastructure Security Scanning） |
| **Dify** | [langgenius/dify](https://github.com/langgenius/dify) | 129K+ stars；低代码 LLM 应用平台；可视化 Pipeline 构建；RAG + Agent + 工作流三合一；最快从原型到生产 |
| **n8n** | [n8n-io/n8n](https://github.com/n8n-io/n8n) | 150K+ stars；400+ 集成；AI-native 工作流；可同时作为 MCP 客户端和 MCP 服务器；自托管 + 公平代码许可 |
| **Langflow** | [langflow-ai/langflow](https://github.com/langflow-ai/langflow) | 拖拽式 RAG + Agent 工作流设计器；基于 LangChain；API 一键发布 |
| **Flowise** | [FlowiseAI/Flowise](https://github.com/FlowiseAI/Flowise) | 42K+ stars；可视化 Agent 构建器；**2025 年 8 月被 Workday 收购**；开源部分持续维护；支持多 Agent 编排、RAG Pipeline、调试与评估全流程 |
| **Pathway** | [pathwaycom/pathway](https://github.com/pathwaycom/pathway) | 50K+ stars；**实时数据 + AI Agent 融合**的专用平台；LLM 应用持续接收数据流更新；Kafka、REST API、文件系统等数据源；适合需要实时知识的 Agent |

---

## 🦞 个人 AI Agent

将 Agent 嵌入你日常使用的消息应用，以自然语言控制真实世界的操作。这是 2026 年增速最快的 Agent 子类别。

| 项目 | GitHub | Stars | 说明 |
|---|---|---|---|
| ⭐ **OpenClaw** | [openclaw/openclaw](https://github.com/openclaw/openclaw) | 247K+ | **2026 年最热门开源 Agent**。60 天从 9K 到 210K+ stars；TypeScript；本地优先自托管；以 WhatsApp / Telegram / Discord 等消息应用为 UI；Skills/Plugins/MCP 三层能力扩展；ClawHub 上 13,729 个社区 Skill。详见 [Awesome-OpenClaw](https://github.com/EthanYolo01/Awesome-OpenClaw) |
| **Open Interpreter** | [OpenInterpreter/open-interpreter](https://github.com/OpenInterpreter/open-interpreter) | 60K+ | 让 LLM 在本地执行代码；可控制文件系统、浏览器、运行任意程序；终端 UI；`01 Project` 延伸为 AI 设备生态 |
| **Letta（前 MemGPT）** | [letta-ai/letta](https://github.com/letta-ai/letta) | 15K+ | 有状态 Agent 平台；持久记忆是核心差异化；跨会话学习；`Conversations` 功能支持多并发体验共享记忆；LLM Agent 的「记忆」系统标杆 |
| **Taxy.ai** | [TaxyAI/browser-extension](https://github.com/TaxyAI/browser-extension) | 2K+ | 浏览器扩展形式的个人 Agent；自然语言控制浏览器操作 |

---

## 💻 代码 Agent

让 AI 真正理解、编写、修改和调试代码的专用 Agent。2026 年该领域竞争最激烈。

### 商业代码 Agent（闭源）

| Agent | 说明 | 基准 |
|---|---|---|
| **Claude Code** | Anthropic 官方 CLI；终端原生；Agent Teams 多 Agent 协作 | SWE-bench Verified **80.9%**（业内最高） |
| **Codex CLI** | OpenAI 终端 Agent；支持多模型 | SWE-bench 业内领先 |
| **Devin 2.0** | Cognition Labs；完全自主；沙盒云环境；Interactive Planning | 业内首个商业代码 Agent |
| **GitHub Copilot Workspace** | Issue → PR 全流程；Copilot Agent Mode in VS Code | 深度 GitHub 集成 |

### 开源代码 Agent

| 项目 | GitHub | Stars | 说明 |
|---|---|---|---|
| ⭐ **OpenHands（前 OpenDevin）** | [All-Hands-AI/OpenHands](https://github.com/All-Hands-AI/OpenHands) | 61K+ | 最活跃的开源自主软件工程 Agent。沙盒执行环境；支持任意 LLM；GitHub Issue → PR 全流程自动化；容器化隔离保证安全 |
| ⭐ **Aider** | [paul-gauthier/aider](https://github.com/paul-gauthier/aider) | 33K+ | 终端代码编辑 Agent；Git 原生（每次修改自动提交）；支持任意 LLM；整个代码库上下文感知；架构师 + 编辑器双模式 |
| **Cline** | [cline/cline](https://github.com/cline/cline) | 35K+ | VS Code 插件形式；完整终端 + 浏览器访问权限；Human-in-the-loop 审批每个操作；MCP 原生支持；支持任意 LLM |
| **SWE-agent** | [princeton-nlp/SWE-agent](https://github.com/princeton-nlp/SWE-agent) | 15K+ | 普林斯顿出品；Agent-Computer Interface（ACI）设计理念；SWE-bench 基准数据集来源；学术研究首选 |
| **Roo-Code** | [RooVetGit/Roo-Code](https://github.com/RooVetGit/Roo-Code) | 25K+ | Cline 分支；结构化模式（Architect/Code/Ask/Debug）；减少幻觉；更严格的上下文控制 |
| **Continue.dev** | [continuedev/continue](https://github.com/continuedev/continue) | 25K+ | VS Code + JetBrains 双插件；开源 AI 编码助手；本地和云端模型均支持；Tab 自动补全 + 对话 + Edit 三合一 |
| **Agentless** | [OpenAutoCoder/Agentless](https://github.com/OpenAutoCoder/Agentless) | 3K+ | 无框架方法的代码修复；无需复杂 Agent 基础设施；SWE-bench 高分；简洁实现的示范 |

### 代码安全审查 Agent

| 项目 | 说明 |
|---|---|
| **CodeRabbit** | AI PR 审查；内联建议；安全漏洞检测；自然语言总结 |
| **Ellipsis** | AI PR 审查员；上下文感知；自动描述、审查、改进 PR |
| **Greptile** | 理解整个代码库上下文的 AI 代码审查；企业级上下文引擎 |

---

## 🌐 浏览器与计算机控制 Agent

让 AI 真正「看屏幕、动鼠标、敲键盘」——Computer Use 能力是 2025-2026 年 Agent 最重要的能力扩展之一。

### 商业产品

| Agent | 说明 |
|---|---|
| **Claude Computer Use** | Anthropic 的桌面/浏览器控制能力；截图驱动；beta 阶段 |
| **OpenAI Operator** | ChatGPT 自主网页 Agent；Human-in-the-loop 检查点；CUA（Computer Use Architecture） |
| **Microsoft Fara** | 70 亿参数 PC 自动化专用模型；配合 Windows Copilot 实现 GUI 操作 |
| **Browser Operator（Dia）** | 自主数字员工；已被 Meta 收购 |

### 开源框架与工具

| 项目 | GitHub | Stars | 说明 |
|---|---|---|---|
| ⭐ **Playwright MCP** | [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) | 15K+ | 最广泛使用的浏览器 Agent 工具；通过 MCP 协议连接任意 Agent 框架；全功能浏览器控制 |
| **Browser Use** | [browser-use/browser-use](https://github.com/browser-use/browser-use) | 60K+ | 高级浏览器自动化；视觉驱动（GPT-4V）；无需代码化选择器；直接操作 DOM 和视觉元素 |
| **Browserbase** | [browserbase/stagehand](https://github.com/browserbase/stagehand) | 10K+ | Stagehand：AI 优先的浏览器自动化框架；云端无头浏览器基础设施；企业级稳定性 |
| **UI-TARS** | [bytedance/UI-TARS](https://github.com/bytedance/ui-tars) | 12K+ | ByteDance 出品；GUI Agent 基础模型；视觉语言模型驱动的计算机控制；2026 年 2 月登顶 GitHub Trending |
| **Agent S2（Simular）** | [simular-ai/Agent-S](https://github.com/simular-ai/Agent-S) | 3K+ | OSWorld 50-step SOTA（34.5%）；多组件专家混合架构；长动作序列稳定性优秀 |
| **Skyvern** | [Skyvern-AI/skyvern](https://github.com/Skyvern-AI/skyvern) | 12K+ | 可靠的网页自动化 API；CAPTCHA 处理；生产级稳定性 |
| **Firecrawl** | [mendableai/firecrawl](https://github.com/mendableai/firecrawl) | 85K+ | 将任意网页转为 LLM 友好 Markdown；去噪；爬虫 + MCP 双模式 |

### 应用测试 Agent

| Agent | 说明 |
|---|---|
| **[agent-qa](https://vostride.com)** | 面向开发者的自然语言 Web、Android 和 iOS 测试工具，结合持久化记忆与经过验证的自我改进，支持 CLI/MCP 工作流。[源码](https://github.com/vostride/agent-qa) · FSL-1.1-ALv2。 |

---

## 🔬 研究与深度探索 Agent

专为研究、信息检索和知识综合设计的 Agent。

| 项目 | GitHub | Stars | 说明 |
|---|---|---|---|
| ⭐ **GPT Researcher** | [assafelovic/gpt-researcher](https://github.com/assafelovic/gpt-researcher) | 21K+ | 并行化深度研究；主 Agent 分解问题 → 多个执行 Agent 并行搜索 → 综合报告；速度快、偏差低 |
| **LangManus** | [Darwin-lfl/langmanus](https://github.com/Darwin-lfl/langmanus) | 31K+ | ByteDance 开源；开源 SuperAgent；研究 + 编码 + 创作三合一；Agent 套件工具 + 沙盒执行 |
| **Manus** | 商业产品 | — | ByteDance 的商业 Agent 产品；自主数字员工；任务级别从分钟到小时 |
| **Perplexica** | [ItzCrazyKns/Perplexica](https://github.com/ItzCrazyKns/Perplexica) | 33K+ | 开源 AI 搜索引擎替代品；深度研究模式；RAG + 搜索融合 |
| **Storm (Stanford)** | [stanford-oval/storm](https://github.com/stanford-oval/storm) | 18K+ | 斯坦福出品；从互联网收集信息生成类维基百科长文；多视角问答；NAACL 2024 最佳论文 |

---

## 🧠 Agent 记忆系统

记忆是 Agent 从「单次问答工具」进化为「真正助手」的关键能力。这个领域在 2025-2026 年经历了爆发式发展。

### 记忆框架与工具

| 项目 | GitHub | 说明 |
|---|---|---|
| ⭐ **MemOS** | [MemTensor/MemOS](https://github.com/MemTensor/MemOS) | **记忆操作系统**。将记忆提升为一等公民：MemCube（统一记忆对象）封装参数记忆、激活记忆、外部存储；跨任务技能复用和记忆进化。有 OpenClaw 插件（降低 72% Token 使用量） |
| ⭐ **mem0** | [mem0ai/mem0](https://github.com/mem0ai/mem0) | 35K+ stars。自我改进的个性化记忆层；自动提取和更新用户偏好；跨 Agent 框架通用；LongMemEval 排行榜高分 |
| **Letta（前 MemGPT）** | [letta-ai/letta](https://github.com/letta-ai/letta) | 有状态 Agent 开发环境；自管理上下文压缩；Agent Development Environment (ADE) |
| **Graphiti（Zep）** | [getzep/graphiti](https://github.com/getzep/graphiti) | 时序知识图谱；记忆具备时间维度；适合需要追踪「什么时候发生了什么」的长时程 Agent |
| **ReMe** | [agentscope-ai/ReMe](https://github.com/agentscope-ai/ReMe) | 阿里 AgentScope 团队出品；记忆提取 + 精化 + 检索完整工具包；多后端向量存储支持 |
| **Cognee** | [topoteretes/cognee](https://github.com/topoteretes/cognee) | 知识图谱 + 向量搜索融合；Agent 可信记忆层；结构化知识管理 |
| **Supermemory** | [supermemoryai/supermemory](https://github.com/supermemoryai/supermemory) | 托管外部记忆服务；语义搜索；多 Agent 实例共享记忆；开源 + 云服务 |

### 记忆相关学术资源

| 资源 | 说明 |
|---|---|
| [Memory in the Age of AI Agents 综述](https://arxiv.org/abs/2512.13564) | 迄今最全的 Agent 记忆综述；统一分类法；HuggingFace 日报 #1 |
| [Awesome-Agent-Memory](https://github.com/TeleAI-UAGI/Awesome-Agent-Memory) | 记忆系统专项论文和资源列表；持续更新 |
| [Agent-Memory-Paper-List](https://github.com/Shichun-Liu/Agent-Memory-Paper-List) | 按记忆类型分类的论文合集 |
| [MemoryAgentBench（ICLR 2026）](https://github.com/HUST-AI-HYZ/MemoryAgentBench) | 通过增量多轮交互评估 LLM Agent 记忆能力的基准 |

---

## 🛠️ 工具与集成

### 工具调用框架

| 工具 | GitHub | 说明 |
|---|---|---|
| ⭐ **Composio** | [ComposioHQ/composio](https://github.com/ComposioHQ/composio) | **1,000+ 工具一次接入**。统一认证管理；搜索工具；上下文管理；沙盒工作台。27K+ stars；兼容所有主流 Agent 框架和 MCP |
| **Toolhouse** | [toolhouseai](https://github.com/toolhouseai) | 云端工具存储与执行；一行代码给 Agent 装备工具；内置工具市场 |
| **AgentRPC** | [agentrpc/agentrpc](https://github.com/agentrpc/agentrpc) | 跨语言、跨网络边界调用任意函数；让 Agent 使用任意语言编写的工具 |

### 代码执行沙盒

| 工具 | GitHub | 说明 |
|---|---|---|
| ⭐ **E2B** | [e2b-dev/e2b](https://github.com/e2b-dev/e2b) | 专为 AI Agent 设计的安全代码执行沙盒；毫秒级启动；Python / JS / 任意语言；云端托管 |
| **Daytona** | [daytonaio/daytona](https://github.com/daytonaio/daytona) | 安全的 AI 生成代码运行时；DAST 安全扫描；Kubernetes 原生 |
| **Modal** | [modal-labs/modal-client](https://github.com/modal-labs/modal-client) | 无服务器 GPU 计算；Agent 任务的弹性执行环境 |

### 本地模型运行

Agent 的本地化部署离不开本地模型运行工具，彻底解决隐私、成本和离网问题：

| 工具 | GitHub | Stars | 说明 |
|---|---|---|---|
| ⭐ **Ollama** | [ollama/ollama](https://github.com/ollama/ollama) | 130K+ | **本地 LLM 运行首选**。一行命令下载运行 Llama、Qwen、Gemma、DeepSeek 等主流开源模型；macOS/Windows/Linux 均支持；REST API 兼容 OpenAI 接口，所有 Agent 框架直接接入；隐私优先，数据零出境 |
| **LM Studio** | [lmstudio-ai/lmstudio.js](https://github.com/lmstudio-ai/lmstudio.js) | 5K+ | 本地模型运行的图形化工具；GGUF 格式；内置 OpenAI 兼容服务器；适合不熟悉命令行的用户 |
| **Jan** | [janhq/jan](https://github.com/janhq/jan) | 28K+ | 完全离线的 AI 助手桌面应用；本地模型 + 远程 API 双模式；100% 隐私 |

### Agent 通信协议

| 协议 | 说明 |
|---|---|
| **MCP（Model Context Protocol）** | Anthropic 发起，现 Linux 基金会中立标准。Agent ↔ 工具通信协议。详见 [Awesome-MCP](https://github.com/EthanYolo01/Awesome-MCP) |
| **A2A（Agent-to-Agent）** | [a2aproject/A2A](https://github.com/a2aproject/A2A) — Google 发起的 Agent 间通信开放协议；CrewAI 已支持；LangGraph 适配中 |
| **ACP（Agent Communication Protocol）** | [agentcommunicationprotocol.dev](https://agentcommunicationprotocol.dev) — 更广泛的 Agent 互操作协议 |

---

## 📊 可观测性、评估与基准测试

**Agent 进入生产环境后，「能不能用」比「能不能跑」更重要。** 这个领域在 2025-2026 年从研究走向工程刚需。

### 可观测性与追踪

| 工具 | 说明 |
|---|---|
| ⭐ **LangSmith** | LangChain 官方可观测性平台；追踪每一步 LLM 调用；A/B 测试；评估套件；生产监控告警 |
| ⭐ **Langfuse** | [langfuse/langfuse](https://github.com/langfuse/langfuse) — 开源 LLM 可观测性；框架无关；自托管可选；追踪、评估、提示管理三合一 |
| **AgentOps** | 专为 Agent 设计的追踪平台；Session replay；成本分析；错误分类 |
| **Weave (W&B)** | Weights & Biases 的 LLM 评估和追踪工具；实验管理 |
| **Helicone** | LLM 请求代理 + 可观测性；缓存；速率限制；成本追踪 |
| **Arize Phoenix** | [Arize-ai/phoenix](https://github.com/Arize-ai/phoenix) — 开源 AI 可观测性；RAG 评估；Embedding 可视化 |

### 代码 Agent 基准测试

| 基准 | 说明 | 2026 年 SOTA |
|---|---|---|
| **SWE-bench Verified** | 在真实 GitHub Issue 上测试代码修复能力；500 个经人工验证的问题 | Claude Code：**80.9%** |
| **SWE-bench Lite** | SWE-bench 的精简版（300 问题）；更快评估 | Claude Code / OpenHands 领先 |
| **LiveCodeBench** | 实时更新的编程竞赛题；防数据污染 | Frontier 模型持续竞争中 |
| **HumanEval / MBPP** | 经典代码生成基准；已被 SWE-bench 系列取代作为主要指标 | 近乎饱和 |

### 计算机控制基准测试

| 基准 | 说明 | 2026 年 SOTA |
|---|---|---|
| **OSWorld** | 桌面 GUI 操作环境；15-step 和 50-step 任务 | Agent S2（Simular）：34.5%（50-step） |
| **WebArena** | 网页交互任务模拟器 | 多框架竞争 |
| **GAIA** | 通用 AI Agent 基准；多步骤真实世界任务 | 各 Agent 框架持续竞争 |

### Agent 综合评估框架

| 工具 | 说明 |
|---|---|
| **AgentBench** | [THUDM/AgentBench](https://github.com/THUDM/AgentBench) — 8 种真实世界环境的统一 Agent 评估框架 |
| **PromptFoo** | [promptfoo/promptfoo](https://github.com/promptfoo/promptfoo) — LLM 应用测试框架；红队测试；自动化评估 |
| **Maxim AI** | 在线评估 + 追踪 + 人工审核工作流；生产 Agent 质量保证 |

---

## 🔒 Agent 安全

Agent 拥有广泛的工具调用和系统访问权限，安全不是可选项。

### 主要威胁

| 威胁类型 | 说明 | 缓解方式 |
|---|---|---|
| **提示注入（Prompt Injection）** | 恶意内容通过工具返回值劫持 Agent 行为 | 输出清理；工具返回值验证；Agent 宪法约束 |
| **工具滥用** | Agent 调用超出必要范围的工具或权限 | 最小权限原则；工具白名单；Human-in-the-loop |
| **数据泄露** | Agent 访问并泄露敏感信息 | 访问控制；数据脱敏；审计日志 |
| **目标偏移（Goal Drift）** | Agent 在长时程任务中偏离原始目标 | 定期检查点；目标对齐验证；人工监督 |
| **失控行动** | Agent 执行不可逆的高风险操作 | 写操作需审批；沙盒执行；回滚机制 |
| **供应链攻击** | 恶意 Agent 工具或 MCP 服务器 | 工具来源验证；mcp-scan；代码审查 |

### 安全工具

| 工具 | 说明 |
|---|---|
| **mcp-scan** | [invariantlabs-ai/mcp-scan](https://github.com/invariantlabs-ai/mcp-scan) — MCP 工具安全扫描；检测提示注入、工具中毒 |
| **Guardrails AI** | [guardrails-ai/guardrails](https://github.com/guardrails-ai/guardrails) — LLM 输入输出护栏；格式验证；内容过滤 |
| **NeMo Guardrails** | [NVIDIA/NeMo-Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) — NVIDIA 出品；对话 AI 安全护栏；主题限制；事实核查 |
| **BoostSecurity** | 防止 AI Agent 引入有漏洞的依赖包；CI/CD 集成 |
| **Rebuff** | [woop/rebuff](https://github.com/woop/rebuff) — 提示注入防御框架；启发式 + LLM 双重检测 |
| **LakeraGuard** | 企业级 AI 安全 API；实时检测提示注入和数据泄露 |

### 安全最佳实践

1. **最小权限原则** — Agent 只应拥有完成当前任务所需的最少权限
2. **Human-in-the-loop（HITL）** — 写操作、不可逆操作、高风险决策必须经人工审批
3. **沙盒执行** — 代码执行在隔离环境（E2B、Docker）中进行，防止系统污染
4. **审计日志** — 记录所有工具调用，支持事后审查和问责
5. **输入输出清理** — 工具返回值视为不可信输入，必须验证和清理
6. **定期检查点** — 长时程任务中周期性验证 Agent 是否仍在正确轨道上

**延伸阅读：**
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [OWASP Agentic Security Initiative](https://genai.owasp.org/initiatives/agentic-security-initiative/)
- [MITRE ATLAS — AI 攻击知识库](https://atlas.mitre.org)

---

## 🤖 具身 Agent 与机器人

将 Agent 能力延伸到物理世界——机器人、家庭助手、工业自动化。

| 项目 | GitHub | 说明 |
|---|---|---|
| **LeRobot（HuggingFace）** | [huggingface/lerobot](https://github.com/huggingface/lerobot) | 38K+ stars；真实机器人的端到端深度学习；teleoperation 数据集；开箱即用的机器学习工具链 |
| **ROS 2** | [ros2/ros2](https://github.com/ros2/ros2) | 机器人操作系统 2.0；机器人软件开发事实标准；LLM 集成插件生态持续增长 |
| **Genesis** | [Genesis-Embodied-AI/Genesis](https://github.com/Genesis-Embodied-AI/Genesis) | 具身 AI 和机器人物理模拟平台；43M 多边形 / 秒渲染速度 |
| **π0（Physical Intelligence）** | 商业产品 | 通用机器人基础模型；跨机器人类型的通用技能转移 |

---

## 📖 教程、博客与文章

### 官方文档与入门

- [LangChain Agent 文档](https://python.langchain.com/docs/how_to/#agents) — 工具调用、ReAct、自定义 Agent 完整指南
- [LangGraph 快速开始](https://langchain-ai.github.io/langgraph/tutorials/introduction/) — 从零构建状态机 Agent
- [OpenAI Agents SDK 文档](https://openai.github.io/openai-agents-python/) — Multi-Agent、Handoffs、Guardrails 详解
- [Google ADK 文档](https://google.github.io/adk-docs/) — Gemini 驱动的 Agent 开发工具包
- [AutoGen 文档](https://microsoft.github.io/autogen/) — 多 Agent 对话框架完整指南
- [HuggingFace Agent Course](https://github.com/huggingface/agents-course) ⭐ — **免费开源 Agent 开发课程**；涵盖 smolagents、LlamaIndex、LangGraph；结业颁证

### 深度技术文章

- [2026 年 AI Agent 框架决策指南](https://dev.to/linou518/the-2026-ai-agent-framework-decision-guide-langgraph-vs-crewai-vs-pydantic-ai-b2h) — LangGraph vs CrewAI vs Pydantic AI 实战对比
- [10 个最佳 AI Agent 框架对比（2026）](https://arsum.com/blog/posts/ai-agent-frameworks/) — 含决策矩阵的深度框架分析
- [Langfuse：开源 Agent 框架完整对比](https://langfuse.com/blog/2025-03-19-ai-agent-comparison) — 12 个框架的全面分析
- [OpenAI：面向生产的实用 Agent 指南](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf) — 架构模式、护栏设计、生产注意事项
- [Letta：AI Agent 技术栈全景](https://www.letta.com/blog/ai-agents-stack) — 2025 年 Agent 技术栈分层解析
- [GAIA 基准：通用 AI Agent 还差多远](https://arxiv.org/abs/2311.12983) — Agent 能力与人类水平的量化差距分析
- [LangChain：Agent 工程现状报告（2026）](https://www.langchain.com/state-of-agent-engineering) — 1,300+ 从业者调研；57% 已在生产部署 Agent；32% 将质量列为最大障碍；89% 已实施可观测性
- [Firecrawl：最佳开源 Agent 框架完整对比（2026）](https://www.firecrawl.dev/blog/best-open-source-agent-frameworks) — LangGraph 34.5M 月下载量、Dify 129K stars 等关键数据；含 Anthropic/OpenAI/McKinsey 的 10 条生产建议
- [ByteByteGo：2026 年 GitHub 顶级 AI 仓库](https://blog.bytebytego.com/p/top-ai-github-repositories-in-2026) — 系统梳理 OpenClaw、n8n、Langflow、Dify 等 2026 年最热门项目的定位与差异
- [Asher Technologies：2026 年 Agent 框架、平台和协议全景](https://ashertech.ca/blog/agentic-ai-tools-guide-2026) — 最全面的框架生态梳理；包含 Microsoft Agent Framework 合并事件、$78 亿市场规模数据

### 学习路径

**入门（了解 AI Agent 是什么）：**
1. 读上方**核心概念速查**章节理解基本原语
2. 安装 [Claude Desktop](https://claude.ai/download) 体验 Agent + MCP 工具调用
3. 用 [smolagents](https://github.com/huggingface/smolagents) 写第一个 Agent（~50 行代码）
4. 跟着 [HuggingFace Agent Course](https://github.com/huggingface/agents-course) 系统学习

**开发者（构建生产 Agent）：**
1. 先用 **CrewAI** 快速验证业务想法（最低上手成本）
2. 需要精确控制时迁移到 **LangGraph**（图状态机 + 检查点）
3. TypeScript 技术栈选 **Mastra** 或 **VoltAgent**
4. 从一开始就集成 **LangSmith** 或 **Langfuse** 追踪（不要等到出问题再加）

---

## 📚 论文与学术资源

### 奠基性论文

| 论文 | 年份 | 意义 |
|---|---|---|
| [ReAct: Synergizing Reasoning and Acting](https://arxiv.org/abs/2210.03629) | 2022 | 奠基性工作：「思考-行动-观察」范式；当前主流 Agent 循环的理论基础 |
| [Chain-of-Thought Prompting](https://arxiv.org/abs/2201.11903) | 2022 | 推理能力的基础；CoT 是所有高级 Agent 推理的前提 |
| [Toolformer: Language Models Can Teach Themselves to Use Tools](https://arxiv.org/abs/2302.04761) | 2023 | 自监督工具使用学习；奠定工具调用的研究基础 |
| [HuggingGPT: Solving AI Tasks with ChatGPT](https://arxiv.org/abs/2303.04671) | 2023 | 多模型协作编排；LLM 作为任务规划者的范式 |
| [Voyager: An Open-Ended Embodied Agent with LLMs](https://arxiv.org/abs/2305.16291) | 2023 | Minecraft 中的终身学习 Agent；技能库持续扩展 |

### 近期重要论文（2025-2026）

| 论文 | 年份 | 说明 |
|---|---|---|
| [Agentic Reasoning for Large Language Models](https://arxiv.org/abs/2601.12538) | 2026 | 全面综述 Agent 推理能力；分类框架；评估体系 |
| [Memory in the Age of AI Agents: A Survey](https://arxiv.org/abs/2512.13564) | 2025/2026 | Agent 记忆系统最全综述；HuggingFace 日报 #1 |
| [SWE-bench Verified](https://arxiv.org/abs/2310.06770) | 2023/持续更新 | 代码 Agent 标准基准；软件工程能力量化评估 |
| [GAIA: A Benchmark for General AI Assistants](https://arxiv.org/abs/2311.12983) | 2023/持续更新 | 通用 Agent 能力评估；测试真实世界多步骤任务 |
| [MemoryAgentBench（ICLR 2026）](https://arxiv.org/abs/2507.05257) | 2025 | 增量多轮交互的 Agent 记忆评估基准 |
| [A Survey on LLM-based Autonomous Agents](https://arxiv.org/abs/2308.11432) | 2023 | 自主 Agent 系统综述；构建 + 应用 + 评估三维分析 |

### 论文与资源合集

| 合集 | 说明 |
|---|---|
| [awesome-ai-agent-papers（VoltAgent）](https://github.com/VoltAgent/awesome-ai-agent-papers) | 2026 年 Agent 论文精选；每周从 arXiv 更新；覆盖多 Agent、记忆、评估、安全 |
| [Awesome-Agentic-Reasoning](https://github.com/weitianxin/Awesome-Agentic-Reasoning) | 基于 ICLR 2026 论文的 Agent 推理资源列表 |
| [Awesome-Agent-Memory](https://github.com/TeleAI-UAGI/Awesome-Agent-Memory) | Agent 记忆系统专项论文和工具 |

---

## 🗺️ 相关 Awesome 列表

| 列表 | 说明 |
|---|---|
| [caramaschiHG/awesome-ai-agents-2026](https://github.com/caramaschiHG/awesome-ai-agents-2026) | 2026 年最全 Agent 列表；300+ 资源，20+ 分类；月度更新 |
| [e2b-dev/awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents) | e2b 维护的经典列表；覆盖自主 Agent 和 SDK |
| [kyrolabs/awesome-agents](https://github.com/kyrolabs/awesome-agents) | 框架和工具导向的 Agent 列表；更新频繁 |
| [kaushikb11/awesome-llm-agents](https://github.com/kaushikb11/awesome-llm-agents) | LLM 框架和工具精选；2026-03-15 更新 |
| [slavakurilyak/awesome-ai-agents](https://github.com/slavakurilyak/awesome-ai-agents) | 300+ 资源；按 Stars 排序 |
| [EthanYolo01/Awesome-OpenClaw](https://github.com/EthanYolo01/Awesome-OpenClaw) | OpenClaw 个人 AI Agent 框架资源（同系列） |
| [EthanYolo01/Awesome-MCP](https://github.com/EthanYolo01/Awesome-MCP) | MCP 协议资源合集（同系列） |

---

## 🤝 如何贡献

欢迎贡献！本列表追求**有效性验证 + 有观点的精选**，而非无脑堆砌。

**提交前请确认：**
1. 链接真实有效（亲自访问确认）
2. 包含清晰说明（是什么、面向谁、为什么值得收录）
3. 没有重复条目（先搜索再提交）
4. 遵循现有章节的格式

**联系维护者：** kalayolo86@gmail.com

---

<div align="center">

**觉得有用？** 给个 ⭐ 并分享给你的团队。
**发现遗漏或死链？** [提 Issue](https://github.com/EthanYolo01/Awesome-Agent/issues) 或提交 PR。

*最后更新：2026 年 3 月 · 由社区用 ❤️ 维护*

🌐 语言切换 / Language：**中文** | [English](README.md)

</div>
