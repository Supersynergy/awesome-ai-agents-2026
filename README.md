# Awesome AI Agents 2026

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Updated](https://img.shields.io/badge/Updated-March%202026-blue.svg)](https://github.com/Supersynergy/awesome-ai-agents-2025)

> Complete directory of AI agents, frameworks, platforms, and tools — March 2026 Edition. Covers 100+ tools across coding agents, multi-agent patterns, MCP/A2A protocols, memory, observability, and security.

**57% of enterprises** have AI agents in production. **73% of Fortune 500** are deploying multi-agent workflows. This list cuts through the noise.

---

## Table of Contents

1. [Agent Frameworks (Production-Ready)](#1-agent-frameworks-production-ready)
2. [Agent Platforms & Products](#2-agent-platforms--products)
3. [Coding Agents](#3-coding-agents)
4. [Protocols & Standards](#4-protocols--standards)
5. [Multi-Agent Patterns](#5-multi-agent-patterns)
6. [Agent Memory](#6-agent-memory)
7. [Agent Observability](#7-agent-observability)
8. [Agent Security & Guardrails](#8-agent-security--guardrails)
9. [Voice Agents](#9-voice-agents)
10. [Agent Deployment](#10-agent-deployment)
11. [RAG & Knowledge](#11-rag--knowledge)
12. [Key Stats (March 2026)](#12-key-stats-march-2026)
13. [Related Awesome Lists](#13-related-awesome-lists)

---

## 1. Agent Frameworks (Production-Ready)

| Framework | Stars | Key Feature | Best For |
|-----------|-------|-------------|----------|
| [LangGraph](https://github.com/langchain-ai/langgraph) 1.0.8 | 19K+ | Durable execution, DAG-based state machines | Complex stateful workflows, production pipelines |
| [CrewAI](https://github.com/crewAIInc/crewAI) 2.x | 38K+ | Role-based multi-agent crews, task delegation | Team simulations, parallel agent collaboration |
| [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) | 12K+ | Routines + handoffs (replaces Swarm) | OpenAI-native agent workflows, voice integration |
| [Claude Agent SDK](https://docs.anthropic.com/agents) | — | MCP-native, hooks, memory, skills, worktrees | Anthropic-native, Claude Code extensions |
| [Google ADK](https://github.com/google/adk-python) | 8K+ | A2A protocol native, Vertex AI integration | Google Cloud agents, A2A interoperability |
| [Microsoft AutoGen](https://github.com/microsoft/autogen) 0.4+ | 50K+ | Multi-agent conversation, actor model | Research, enterprise multi-agent dialogue |
| [Pydantic AI](https://github.com/pydantic/pydantic-ai) | 11K+ | Type-safe agents, validated structured outputs | Production APIs, strict output contracts |
| [SmolAgents](https://github.com/huggingface/smolagents) | 18K+ | Minimalist CodeAgent, ~1K lines core | Learning, lightweight deployments, HuggingFace models |
| [AG2](https://github.com/ag2ai/ag2) | 7K+ | Community AutoGen fork, faster releases | AutoGen users wanting community-driven roadmap |
| [LangChain](https://github.com/langchain-ai/langchain) | 116K+ | Massive ecosystem, 1000+ integrations | Prototyping, integration-heavy workflows |
| [Agno](https://github.com/agno-agi/agno) | 35K+ | Multimodal agents, runtime + control plane | Multimodal tasks, agent observability |
| [Composio](https://github.com/composio/composio) | 27K+ | 100+ tool integrations, MCP support | Tool-heavy agents, SaaS automation |

### Local / Open-Source Runtimes

| Framework | Stars | Key Feature | Best For |
|-----------|-------|-------------|----------|
| [Open Interpreter](https://github.com/OpenInterpreter/open-interpreter) | 56K+ | Natural language → code execution | Local automation, full OS control |
| [Dify](https://github.com/langgenius/dify) | 60K+ | Visual workflow builder, self-hosted | Teams wanting GUI agent builder |
| [Flowise](https://github.com/FlowiseAI/Flowise) | 32K+ | Drag-and-drop node editor | Low-code agent building |
| [Goose](https://github.com/block/goose) | 10K+ | Block's extensible agent, MCP-native | Developer automation on local machines |

---

## 2. Agent Platforms & Products

### Autonomous Agents (Cloud)

| Platform | Backing | Key Feature | Notable |
|----------|---------|-------------|---------|
| [Devin 2.0](https://cognition.ai) | Cognition | Autonomous SWE, parallel instances, 30-day project memory | Solves 13.86% SWE-bench (Pro) autonomously |
| [Manus AI](https://manus.ai) | Meta ($2B acq.) | Iterate-loop multi-agent, 100+ tool integrations | Most viral agent demo of early 2026 |
| [OpenAI Deep Research](https://openai.com/research) | OpenAI | 5–30 min autonomous research sessions, citation-backed | GPT-4o + o3 backbone, best research agent |
| [Google Deep Research](https://gemini.google.com) | Google | Gemini 2.0 backbone, integrated Workspace | Best for Google Workspace users |
| [Replit Agent](https://replit.com/ai) | Replit | Full-stack app builder, deploys instantly | Fastest path from idea to live app |
| [Bolt.new](https://bolt.new) | StackBlitz | Instant web app generation, browser-native | Frontend prototypes in seconds |
| [Lovable](https://lovable.dev) | Lovable | Product-focused app builder, Supabase integration | Non-technical founders |
| [v0](https://v0.dev) | Vercel | UI component generation, React/Tailwind | Frontend engineers, design-to-code |

### Enterprise Agent Platforms

| Platform | Key Feature | Best For |
|----------|-------------|----------|
| [Microsoft Copilot Studio](https://copilotstudio.microsoft.com) | Teams + M365 integration, AutoGen backend | Enterprise Microsoft shops |
| [Salesforce Agentforce](https://www.salesforce.com/agentforce) | CRM-native, Einstein AI | Sales and service automation |
| [ServiceNow AI Agents](https://www.servicenow.com) | ITSM-native, workflow automation | IT operations |
| [Workday AI Agents](https://www.workday.com) | HR + Finance workflows | Enterprise HR/Finance teams |

---

## 3. Coding Agents

| Tool | Stars | Architecture | Strength |
|------|-------|--------------|----------|
| [Claude Code](https://claude.ai/code) | — | 1M context, MCP, hooks, skills, memory, worktrees | Deep codebase understanding, agentic loops |
| [Cursor](https://cursor.sh) | — | IDE-native, agent mode, Composer | Best IDE integration, fastest iteration |
| [Windsurf](https://codeium.com/windsurf) | — | Cascade flow, multi-file awareness | Flow-based editing, Codeium integration |
| [Cline](https://github.com/cline/cline) | 28K+ | VS Code extension, any model, MCP | Open source, model-agnostic, community |
| [Aider](https://github.com/Aider-AI/aider) | 25K+ | Terminal, git-aware, pair programming | CLI users, git-native, repo-wide edits |
| [Continue.dev](https://github.com/continuedev/continue) | 20K+ | Open source, any model, VS Code + JetBrains | Privacy-first, self-hosted model support |
| [OpenHands](https://github.com/All-Hands-AI/OpenHands) | 65K+ | Docker-isolated, web UI, MIT license | Sandboxed execution, evaluation benchmarks |
| [SWE-agent](https://github.com/princeton-nlp/SWE-agent) | 15K+ | Princeton, ACI interface, benchmark-driven | Research, SWE-bench evaluation |
| [GitHub Copilot Agent](https://github.com/features/copilot) | — | Tight GitHub integration, code review, PR summaries | GitHub-native workflows |
| [Codex CLI](https://github.com/openai/codex) | 18K+ | Sandboxed execution, terminal, multimodal | OpenAI-native, safe local execution |
| [Amp](https://ampcode.com) | — | Sourcegraph-backed, repo-wide context | Large monorepo navigation |
| [Kiro](https://kiro.dev) | — | Spec-driven development, AWS integration | AWS-native teams |

### SWE-bench Leaderboard (March 2026)

| Agent | SWE-bench Verified | SWE-bench Pro |
|-------|--------------------|---------------|
| OpenHands + Claude Sonnet | 80.0% | — |
| SWE-agent + GPT-4o | 55.0% | — |
| Devin 2.0 | — | 23.7% |
| Amazon Q Developer | 50.0% | — |

---

## 4. Protocols & Standards

### MCP — Model Context Protocol

[github.com/modelcontextprotocol](https://github.com/modelcontextprotocol) | Anthropic | **10,000+ servers** | **97M SDK downloads**

- Universal open standard for connecting AI agents to tools, data, and APIs
- Transport: stdio (local), HTTP+SSE (remote), Streamable HTTP (2025 spec)
- Server types: Tools, Resources, Prompts, Sampling
- Major adopters: VS Code, Claude, Cursor, Windsurf, Zed, JetBrains, Cline
- [MCP Server Hub](https://mcp.so) — discover and share servers

```
Client → MCP Server → Tool/DB/API
         (JSON-RPC 2.0)
```

### A2A — Agent-to-Agent Protocol

[github.com/google/A2A](https://github.com/google/A2A) | Google | **100+ partners** | Linux Foundation project

- Open protocol for agent-to-agent communication, independent of internal architecture
- Agent Cards: JSON discovery files (/.well-known/agent.json)
- Complements MCP: A2A for agent↔agent, MCP for agent↔tool
- Partners: SAP, Salesforce, ServiceNow, MongoDB, Atlassian, Box

### OpenAI Standards

| Standard | Purpose |
|----------|---------|
| [Function Calling](https://platform.openai.com/docs/guides/function-calling) | Tool use, structured outputs |
| [Realtime API](https://platform.openai.com/docs/guides/realtime) | Voice + vision agents |
| [Assistants API](https://platform.openai.com/docs/assistants) | Thread-persistent agents |

---

## 5. Multi-Agent Patterns

| Pattern | Token Cost | Latency | Reliability | Best For |
|---------|------------|---------|-------------|----------|
| **Orchestrator-Worker** | Medium | Medium | High (90.2% improvement) | Production default, parallelizable tasks |
| **Pipeline** | Low | Low | Very High | Sequential, deterministic workflows |
| **Debate / Critique** | High | High | Very High | High-stakes decisions, accuracy-critical |
| **Swarm / Handoffs** | Low–Med | Low | Medium | Customer service, routing, triage |
| **Mixture of Agents** | High | Medium | Highest | Consensus, adversarial robustness |
| **Hierarchical** | Medium | Medium | High | Complex nested tasks, management layers |
| **Reflection** | Medium | Medium | High | Code review, self-improvement loops |

### Pattern Details

**Orchestrator-Worker** — One planning agent decomposes tasks, multiple specialist agents execute in parallel. Delivers 90.2% task completion improvement over single-agent baseline. Production default for 2026.

**Debate / Critique** — Two agents propose + critique solutions. Best accuracy for reasoning-heavy tasks (math, logic, strategy). 30–50% higher accuracy, 2–3x token cost.

**Swarm / Handoffs** — Agents hand off context to specialists based on conversation state. OpenAI's Swarm evolved into the Agents SDK handoff primitive.

---

## 6. Agent Memory

| Tool | Stars | Architecture | Best For |
|------|-------|--------------|----------|
| [Mem0](https://github.com/mem0ai/mem0) | 28K+ | Managed, vector + graph, cross-session | Production apps needing managed memory |
| [Letta / MemGPT](https://github.com/letta-ai/letta) | 14K+ | Stateful agents, editable memory blocks, self-editing | Long-running agents, persistent personas |
| [Zep](https://github.com/getzep/zep) | 7K+ | Temporal knowledge graph, entity tracking | CRM-like memory, relationship tracking |
| [Cognee](https://github.com/topoteretes/cognee) | 5K+ | Knowledge graph + reasoning, GraphRAG | Complex relational knowledge, research |

### Memory Taxonomy

```
Working memory    → Context window (in-prompt)
Episodic memory   → Session history (databases)
Semantic memory   → Vector embeddings (knowledge)
Procedural memory → System prompts, skills, rules
```

---

## 7. Agent Observability

| Tool | Stars | Key Feature | Best For |
|------|-------|-------------|----------|
| [Langfuse](https://github.com/langfuse/langfuse) | 10K+ | Open source, prompt versioning, self-hostable | Privacy-first, LangChain/CrewAI teams |
| [LangSmith](https://smith.langchain.com) | — | Zero-overhead tracing, LangChain ecosystem | LangChain/LangGraph production |
| [AgentOps](https://github.com/AgentOps-AI/agentops) | 3K+ | Session replay, 400+ framework integrations | Framework-agnostic, debugging agents |
| [Braintrust](https://braintrustdata.com) | — | 80x faster evals, dataset management | Evaluation-driven development |
| [Helicone](https://github.com/Helicone/helicone) | 4K+ | Gateway-based, no SDK changes needed | Drop-in observability, any provider |
| [Arize Phoenix](https://github.com/Arize-ai/phoenix) | 6K+ | Open source, LLM evals, embeddings | ML teams, explainability |

### What to Observe

- **Traces**: full agent reasoning chain, tool calls, sub-agent spawns
- **Spans**: latency per step, token cost breakdown
- **Evals**: task success rate, hallucination rate, tool accuracy
- **Replays**: reproduce exact session state for debugging

---

## 8. Agent Security & Guardrails

### Guardrail Frameworks

| Tool | Stars | Approach | Best For |
|------|-------|----------|----------|
| [Guardrails AI](https://github.com/guardrails-ai/guardrails) | 5K+ | Validators on input/output, retry logic | Structured output validation |
| [NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) | 4K+ | Conversation rails, topic control | NVIDIA stack, conversation safety |
| [LLM Guard](https://github.com/laiyer-ai/llm-guard) | 3K+ | Prompt sanitization, PII detection | Enterprise compliance |
| [Rebuff](https://github.com/woop/rebuff) | 2K+ | Prompt injection detection, heuristic + ML | Injection-aware deployments |

### Key Threat Vectors (2026)

| Threat | Description | Mitigation |
|--------|-------------|------------|
| **Prompt Injection** | Malicious content in tool outputs hijacks agent | Input sanitization, sandboxed execution |
| **Tool Poisoning** | Compromised MCP servers return malicious instructions | Server allowlists, output validation |
| **Data Exfiltration** | Agent leaks sensitive context to external tools | Output filtering, egress controls |
| **Agent Impersonation** | Rogue agent spoofs trusted agent identity | A2A auth, signed Agent Cards |
| **Runaway Loops** | Agent gets stuck in infinite tool-call loops | Max steps, circuit breakers, timeouts |

### Secure Agent Checklist

- Sandbox tool execution (Docker, E2B, Daytona)
- Validate all tool inputs and outputs
- Implement max-steps and cost limits
- Use least-privilege API scopes
- Log all tool calls for audit trails
- Human-in-the-loop for irreversible actions

---

## 9. Voice Agents

| Platform | Type | Key Feature | Best For |
|----------|------|-------------|----------|
| [Retell AI](https://retellai.com) | Managed | 500ms latency, interruption handling, CRM integrations | Sales, support call centers |
| [Vapi](https://vapi.ai) | Managed | 600ms latency, 100+ providers, phone numbers | Developers building voice products |
| [Bland AI](https://bland.ai) | Managed | Enterprise-grade, call routing, post-call analysis | High-volume outbound calling |
| [LiveKit Agents](https://github.com/livekit/agents) | Open Source | Real-time audio/video, STT+LLM+TTS pipeline | Self-hosted, custom voice agents |
| [OpenAI Realtime API](https://platform.openai.com/docs/guides/realtime) | API | Native voice, vision, interruption detection | GPT-4o voice integration |
| [ElevenLabs Conversational](https://elevenlabs.io/conversational-ai) | Managed | Ultra-realistic voices, 32 languages | High-fidelity voice quality |

---

## 10. Agent Deployment

### Serverless / Cloud

| Platform | Key Feature | Best For |
|----------|-------------|----------|
| [Modal](https://modal.com) | GPU serverless, sub-second cold starts, cron | Python-native, batch agent jobs |
| [Replicate](https://replicate.com) | Model hosting, prediction API, fine-tuning | ML model deployment, any framework |
| [Together AI](https://together.ai) | Fast inference, 100+ models, fine-tuning | Open model inference at scale |
| [Fireworks AI](https://fireworks.ai) | Fastest open model inference, FireFunction | Low-latency tool-calling agents |
| [E2B](https://github.com/e2b-dev/e2b) | Sandboxed code execution, 150ms boot | Safe code execution inside agents |
| [Daytona](https://github.com/daytonaio/daytona) | Elastic AI code infra, secure workspaces | Coding agent sandboxes |

### Self-Hosted

| Platform | Key Feature | Best For |
|----------|-------------|----------|
| [BentoML](https://github.com/bentoml/BentoML) | Model serving, batching, async | ML engineers, custom inference |
| [Ollama](https://ollama.com) | 100+ models, simple CLI, GPU support | Local development, privacy-first |
| [LocalAI](https://github.com/mudler/LocalAI) | OpenAI-compatible API, any model | Drop-in local OpenAI replacement |
| [vLLM](https://github.com/vllm-project/vllm) | High-throughput serving, PagedAttention | Production local inference at scale |

---

## 11. RAG & Knowledge

### Orchestration Frameworks

| Tool | Stars | Key Feature | Best For |
|------|-------|-------------|----------|
| [LlamaIndex](https://github.com/run-llama/llama_index) | 37K+ | Advanced RAG, structured queries, agents | Complex document understanding |
| [Haystack](https://github.com/deepset-ai/haystack) | 18K+ | Production NLP pipelines, modular | Enterprise search, QA systems |
| [DSPy](https://github.com/stanfordnlp/dspy) | 21K+ | Programmatic LM optimization, signatures | Prompt optimization, research |

### Vector Databases

| Database | Stars | Key Feature | Best For |
|----------|-------|-------------|----------|
| [Qdrant](https://github.com/qdrant/qdrant) | 22K+ | Rust, payload filtering, sparse+dense | Production, fast filtered search |
| [Chroma](https://github.com/chroma-core/chroma) | 17K+ | Embedded, developer-friendly | Prototyping, local development |
| [Weaviate](https://github.com/weaviate/weaviate) | 12K+ | GraphQL, multi-tenancy, hybrid search | Enterprise, multi-tenant SaaS |
| [Milvus](https://github.com/milvus-io/milvus) | 32K+ | Cloud-native, billion-scale | High-scale production |
| [pgvector](https://github.com/pgvector/pgvector) | 14K+ | PostgreSQL extension | PostgreSQL shops, no new infra |
| [Pinecone](https://pinecone.io) | — | Managed, serverless, real-time upserts | Fully managed, no ops burden |

---

## 12. Key Stats (March 2026)

| Metric | Value | Source |
|--------|-------|--------|
| Enterprises with agents in production | **57%** | McKinsey State of AI 2026 |
| Fortune 500 deploying multi-agent workflows | **73%** | Gartner Q1 2026 |
| SWE-bench Verified SOTA | **80%** (OpenHands + Claude) | SWE-bench.org |
| SWE-bench Pro SOTA | **23.7%** (Devin 2.0) | Cognition |
| MCP servers live | **10,000+** | Anthropic |
| MCP SDK downloads | **97M** | Anthropic |
| A2A protocol partners | **100+** | Google |
| Projected agent market by 2028 | **$450B** | Grand View Research |
| Voice agent market CAGR | **34%** | MarketsandMarkets |
| Average agent task completion improvement (multi-agent vs single) | **90.2%** | Stanford HAI 2026 |

### Model Benchmarks (March 2026)

| Model | MMLU | HumanEval | MATH | Context |
|-------|------|-----------|------|---------|
| Claude Sonnet 4 | 90.2% | 92.4% | 86.1% | 1M |
| GPT-4o (March 2026) | 89.7% | 90.1% | 83.4% | 128K |
| Gemini 2.0 Ultra | 91.0% | 88.3% | 88.7% | 1M |
| DeepSeek R2 | 88.9% | 91.2% | 90.1% | 128K |
| Llama 4 Maverick | 85.3% | 84.1% | 79.8% | 1M |

---

## 13. Related Awesome Lists

| List | Stars | Focus |
|------|-------|-------|
| [awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents) | 24K+ | Broad AI agents ecosystem |
| [awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | 18K+ | MCP server directory |
| [500-AI-Agents-Projects](https://github.com/ashishpatel26/500-AI-Agents-Projects) | 16K+ | Real-world agent projects |
| [awesome-llm-agents](https://github.com/kaushikb11/awesome-llm-agents) | 8K+ | LLM-powered agents research |
| [awesome-langchain](https://github.com/kyrolabs/awesome-langchain) | 7K+ | LangChain ecosystem |
| [awesome-local-llm](https://github.com/continuum-llms/chatgpt-memory) | 5K+ | Local model running |
| [awesome-openai-agents](https://github.com/openai/openai-agents-python) | 12K+ | OpenAI Agents SDK examples |
| [awesome-agentic-coding](https://github.com/nicholasgasior/awesome-agentic-coding) | 3K+ | Coding agent tools |

---

## Community

| Resource | Members / Activity |
|----------|--------------------|
| [r/LocalLLaMA](https://reddit.com/r/LocalLLaMA) | 700K+ members |
| [r/AIAgents](https://reddit.com/r/AIAgents) | 150K+ members |
| [LangChain Discord](https://discord.gg/langchain) | 80K+ members |
| [Hugging Face Discord](https://discord.gg/huggingface) | 100K+ members |
| [AI Engineer World's Fair](https://www.ai.engineer) | Annual conference |

---

## Contributing

PRs welcome. Please follow these guidelines:
- Add tools with **GitHub stars, key feature, and best-for use case**
- Keep descriptions to one line — link to official docs for details
- Group by the most relevant section
- Update star counts when significantly outdated (>25% change)

See [CONTRIBUTING.md](CONTRIBUTING.md) for full guidelines.

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

**Last updated: March 2026** | [Report an issue](https://github.com/Supersynergy/awesome-ai-agents-2025/issues) | [Request addition](https://github.com/Supersynergy/awesome-ai-agents-2025/issues/new)
