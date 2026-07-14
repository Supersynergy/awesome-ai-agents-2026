# Awesome AI Agents 2026

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Updated](https://img.shields.io/badge/Updated-July%202026-blue.svg)](https://github.com/Supersynergy/awesome-ai-agents-2025)

> A practical index of AI agent frameworks, runtimes, coding agents, protocols, memory, observability, security, voice, and deployment tools.

This repository keeps its historical `-2025` URL, but the maintained list is the **2026 snapshot**. The current pass was checked on **14 July 2026** against GitHub, `ghmax`, Superweb, Tool Radar, several comparison lists, and YouTube discovery signals.

Stars below are a dated GitHub adoption signal, not a quality claim. Prefer the upstream repository and documentation before selecting a tool.

## How this list is maintained

- **Primary evidence:** official repository or product documentation, active upstream, and a clear use case.
- **Discovery:** `ghmax`, Tool Radar, comparison lists, and YouTube search surface candidates; they do not decide inclusion alone.
- **Freshness:** stale star counts, archived repositories, and unsupported market/benchmark claims are removed from the core snapshot.
- **Audit:** the exact sources, selection decisions, and fallback limits are recorded in [the 14 July update report](docs/UPDATE-2026-07-14.md).

## Table of Contents

1. [Agent Frameworks](#1-agent-frameworks)
2. [Agent Runtimes and Platforms](#2-agent-runtimes-and-platforms)
3. [Coding Agents](#3-coding-agents)
4. [Protocols and Standards](#4-protocols-and-standards)
5. [Multi-Agent Patterns](#5-multi-agent-patterns)
6. [Agent Memory](#6-agent-memory)
7. [Observability and Evaluation](#7-observability-and-evaluation)
8. [Security and Guardrails](#8-security-and-guardrails)
9. [Voice Agents](#9-voice-agents)
10. [Deployment and Sandboxing](#10-deployment-and-sandboxing)
11. [Knowledge and Retrieval](#11-knowledge-and-retrieval)
12. [Current Signals](#12-current-signals)
13. [Related Awesome Lists](#13-related-awesome-lists)
14. [Contributing](#14-contributing)

## 1. Agent Frameworks

| Framework | Stars snapshot | What it is good at |
|-----------|----------------|--------------------|
| [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) | 27.9K | Lightweight multi-agent workflows, tools, handoffs, and tracing |
| [Claude Agent SDK for Python](https://github.com/anthropics/claude-agent-sdk-python) | 7.6K | Building agents around Claude Code primitives and tool use |
| [Google ADK](https://github.com/google/adk-python) | 20.6K | Code-first agents, evaluation, deployment, and Google model integration |
| [Pydantic AI](https://github.com/pydantic/pydantic-ai) | 18.5K | Type-safe agents and validated structured outputs |
| [Mastra](https://github.com/mastra-ai/mastra) | 26.2K | TypeScript agents, workflows, tools, memory, and observability |
| [smolagents](https://github.com/huggingface/smolagents) | 28.4K | Small code-first agents and CodeAgent workflows |
| [Agno](https://github.com/agno-agi/agno) | 41.2K | Model-agnostic agents with tools, knowledge, memory, and runtime controls |
| [mcp-agent](https://github.com/lastmile-ai/mcp-agent) | 8.4K | MCP-native agents and simple workflow patterns |

### Local and extensible runtimes

| Runtime | Stars snapshot | Best fit |
|---------|----------------|----------|
| [OpenClaw](https://github.com/openclaw/openclaw) | 382.9K | Self-hosted assistants, channels, skills, memory, and tool orchestration |
| [Goose](https://github.com/aaif-goose/goose) | 51.2K | Extensible local agent with MCP and any-LLM support |
| [OpenHands](https://github.com/OpenHands/OpenHands) | 80.8K | Open-source software-development agents and sandboxed execution |

## 2. Agent Runtimes and Platforms

| Tool | Delivery | Use case |
|------|----------|----------|
| [OpenAI Deep Research](https://openai.com/index/introducing-deep-research/) | Hosted | Long-running, citation-oriented research tasks |
| [Gemini Deep Research](https://gemini.google.com/) | Hosted | Research tasks in the Google ecosystem |
| [Manus](https://manus.im/) | Hosted | General-purpose autonomous task execution |
| [Replit Agent](https://replit.com/ai) | Hosted | Build and deploy applications from natural language |
| [v0](https://v0.dev/) | Hosted | UI and application generation |
| [Lovable](https://lovable.dev/) | Hosted | Product-oriented application prototyping |
| [OpenClaw](https://github.com/openclaw/openclaw) | Self-hosted | Personal assistant and multi-channel agent runtime |
| [Goose](https://github.com/aaif-goose/goose) | Local / self-hosted | Developer automation with pluggable tools and models |

## 3. Coding Agents

| Agent | Stars snapshot | Interface | Strength |
|-------|----------------|-----------|----------|
| [OpenCode](https://github.com/anomalyco/opencode) | 185.8K | Terminal | Open-source, model-agnostic coding agent |
| [Claude Code](https://github.com/anthropics/claude-code) | 137.9K | Terminal | Repository-aware coding, tools, hooks, and agent workflows |
| [Codex](https://github.com/openai/codex) | 98.0K | Terminal | Open-source terminal agent with sandboxed execution |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | 106.0K | Terminal | Open-source Gemini agent with terminal and MCP workflows |
| [Cline](https://github.com/cline/cline) | 64.7K | VS Code / CLI / SDK | Model-agnostic coding agent with tool execution |
| [OpenHands](https://github.com/OpenHands/OpenHands) | 80.8K | Web / CLI | Autonomous software-development workflows |
| [Aider](https://github.com/Aider-AI/aider) | 47.4K | Terminal | Git-aware pair programming and repository edits |
| [Kimi CLI](https://github.com/MoonshotAI/kimi-cli) | 9.2K | Terminal | Terminal agent with planning and coding workflows |
| [Chorus](https://github.com/chorus-codes/chorus) | 525 | CLI harness | Multi-LLM peer review for code decisions before shipping |

### Coding-agent support

| Tool | Use case |
|------|----------|
| [Claude Code Router](https://github.com/musistudio/claude-code-router) | Route Claude Code workflows across providers and models |
| [Claude Code Templates](https://github.com/davila7/claude-code-templates) | Starter configurations, templates, and deployment recipes |
| [SWE-agent](https://github.com/princeton-nlp/SWE-agent) | Research and benchmark-oriented software-engineering agents |
| [GitHub Copilot](https://github.com/features/copilot) | GitHub-native coding, review, and agent workflows |
| [Cursor](https://cursor.com/) | IDE-native agentic editing |
| [Windsurf](https://windsurf.com/) | IDE and flow-oriented coding assistance |

## 4. Protocols and Standards

| Protocol | Primary source | Purpose |
|----------|----------------|---------|
| [Model Context Protocol (MCP)](https://github.com/modelcontextprotocol/modelcontextprotocol) | [Specification](https://modelcontextprotocol.io/specification/latest) | Connect agents to tools, data, prompts, and resources |
| [MCP Servers](https://github.com/modelcontextprotocol/servers) | Official server repository | Reference servers and MCP implementation examples |
| [Agent2Agent (A2A)](https://github.com/a2aproject/A2A) | [Protocol repository](https://a2a-protocol.org/latest/) | Interoperability and communication between opaque agents |
| [OpenAI function calling](https://platform.openai.com/docs/guides/function-calling) | OpenAI documentation | Structured tool calls and schema-constrained actions |
| [Anthropic tool use](https://docs.anthropic.com/en/docs/build-with-claude/tool-use) | Anthropic documentation | Tool definitions and model-directed actions |

MCP is the agent-to-tool boundary. A2A is the agent-to-agent boundary. They are complementary, not interchangeable.

## 5. Multi-Agent Patterns

| Pattern | Use when | Main control |
|---------|----------|--------------|
| **Pipeline** | Steps are known and ordered | Explicit state between stages |
| **Orchestrator-worker** | Work can be split across specialists | Central planner, bounded workers |
| **Handoff** | A specialist should own the next turn | Typed transfer plus stop conditions |
| **Debate / critique** | A second opinion reduces costly errors | Independent proposal and review |
| **Reflection** | Output can be checked and improved | Separate verifier and retry budget |
| **Human approval** | Actions are costly or irreversible | Approval gate before side effects |

Production rule: define a closed task, a machine-checkable oracle, a maximum step count, and an explicit stop path before adding more agents.

## 6. Agent Memory

| Tool | Stars snapshot | Focus |
|------|----------------|-------|
| [Mem0](https://github.com/mem0ai/mem0) | 60.8K | Memory layer for cross-session agent context |
| [Letta](https://github.com/letta-ai/letta) | 23.8K | Stateful agents and editable long-term memory |
| [Cognee](https://github.com/topoteretes/cognee) | 27.8K | Self-hosted knowledge graph and persistent agent memory |
| [TencentDB-Agent-Memory](https://github.com/TencentCloud/TencentDB-Agent-Memory) | 8.8K | Agent-memory storage and retrieval patterns |

Use memory only when the retention policy, deletion path, tenant boundary, and provenance are explicit.

## 7. Observability and Evaluation

| Tool | Stars snapshot | Focus |
|------|----------------|-------|
| [Langfuse](https://github.com/langfuse/langfuse) | 31.1K | Open-source traces, evals, prompts, datasets, and metrics |
| [Arize Phoenix](https://github.com/Arize-ai/phoenix) | 10.6K | AI observability and evaluation |
| [OpenTelemetry](https://opentelemetry.io/) | — | Vendor-neutral traces, metrics, and logs |
| [SWE-bench](https://github.com/SWE-bench/SWE-bench) | — | Reproducible software-engineering agent evaluation |

Track task success, tool success, latency, token cost, retries, human interventions, and unsafe-action attempts. A transcript alone is not an evaluation.

## 8. Security and Guardrails

| Tool | Focus |
|------|-------|
| [NVIDIA NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails) | Programmable conversation and action rails |
| [Guardrails AI](https://github.com/guardrails-ai/guardrails) | Input/output validation and structured contracts |
| [LLM Guard](https://github.com/protectai/llm-guard) | Prompt sanitization, PII detection, and scanners |
| [garak](https://github.com/NVIDIA/garak) | LLM vulnerability probing and red teaming |
| [Microsoft Presidio](https://github.com/microsoft/presidio) | PII detection and anonymization |

Minimum controls: least-privilege tool scopes, server allowlists, validated tool output, sandboxing, egress limits, max steps, cost limits, audit logs, and human approval for irreversible actions.

## 9. Voice Agents

| Tool | Type | Focus |
|------|------|-------|
| [LiveKit Agents](https://github.com/livekit/agents) | Open source | Realtime audio/video agent pipelines |
| [OpenAI Realtime API](https://platform.openai.com/docs/guides/realtime) | API | Realtime voice and multimodal interaction |
| [Vapi](https://vapi.ai/) | Hosted | Developer-first voice agents and telephony |
| [Retell AI](https://www.retellai.com/) | Hosted | Conversational phone agents |
| [ElevenLabs Conversational AI](https://elevenlabs.io/conversational-ai) | Hosted | Voice quality and conversational interfaces |

## 10. Deployment and Sandboxing

| Tool | Stars snapshot | Use case |
|------|----------------|----------|
| [E2B](https://github.com/e2b-dev/E2B) | 13.0K | Secure environments for agent-generated code |
| [Daytona](https://github.com/daytonaio/daytona) | 72.2K | Elastic infrastructure for AI-generated code |
| [Ollama](https://github.com/ollama/ollama) | 176.1K | Local model serving and developer workflows |
| [llama.cpp](https://github.com/ggml-org/llama.cpp) | 120.4K | Portable local inference in C/C++ |
| [vLLM](https://github.com/vllm-project/vllm) | 86.3K | High-throughput model serving |
| [Modal](https://modal.com/) | — | Serverless compute for agent and model workloads |
| [BentoML](https://github.com/bentoml/BentoML) | — | Packaging and serving model-backed applications |

Sandbox untrusted code. Treat model output as data until a policy layer validates the action.

## 11. Knowledge and Retrieval

| Tool | Focus |
|------|-------|
| [Qdrant](https://github.com/qdrant/qdrant) | Filterable vector search and retrieval |
| [pgvector](https://github.com/pgvector/pgvector) | Vector search inside PostgreSQL |
| [Haystack](https://github.com/deepset-ai/haystack) | Modular search, RAG, and agent pipelines |
| [DSPy](https://github.com/stanfordnlp/dspy) | Programmatic prompt and LM optimization |
| [LlamaIndex](https://github.com/run-llama/llama_index) | Data connectors, indexing, and retrieval workflows |

Choose retrieval storage by deletion semantics, tenant isolation, filter support, provenance, and operational cost—not by embedding demos alone.

## 12. Current Signals

The 14 July Tool Radar run surfaced these current signals:

- **Agent runtime:** [OpenClaw](https://github.com/openclaw/openclaw) ranked first in the local `agent-ai` slice.
- **Coding agent:** [OpenCode](https://github.com/anomalyco/opencode) ranked first in the local `coding-agent` slice.
- **Emerging review workflow:** [Chorus](https://github.com/chorus-codes/chorus) appeared in both agent and coding slices with recent star velocity.
- **YouTube discovery:** current results cluster around agentic coding workflows, MCP versus APIs/skills, and local coding setups. These signals informed discovery only; they are not ranking evidence.

See the exact run, timestamps, comparison-list commits, and YouTube fallback output in [docs/UPDATE-2026-07-14.md](docs/UPDATE-2026-07-14.md).

## 13. Related Awesome Lists

| List | Last checked | Focus |
|------|--------------|-------|
| [e2b-dev/awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents) | 9 Jul 2026 | Broad open- and closed-source agent directory |
| [caramaschiHG/awesome-ai-agents-2026](https://github.com/caramaschiHG/awesome-ai-agents-2026) | 10 Jun 2026 | Broad 2026 catalog with many categories |
| [Zijian-Ni/awesome-ai-agents-2026](https://github.com/Zijian-Ni/awesome-ai-agents-2026) | 2 Jul 2026 | Multilingual 2026 list with changelog and archive flags |
| [Deep-Insight-Labs/awesome-ai-agents](https://github.com/Deep-Insight-Labs/awesome-ai-agents) | 28 Apr 2026 | Frameworks, observability, and emerging projects |
| [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | 14 Jul 2026 | Claude Code skills, plugins, agents, and developer tooling |
| [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | 13 Jul 2026 | MCP server discovery |

Use broad lists for recall. Use this list's dated audit and upstream links for currentness.

## 14. Contributing

Before adding an entry:

1. Link to the official upstream or product documentation.
2. State one concrete capability and one target user/use case.
3. Check that the project is active, documented, and not archived.
4. Avoid unsupported market share, benchmark, pricing, or adoption claims.
5. Add the date and source when a claim is time-sensitive.

PRs are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT License — see [LICENSE](LICENSE).

**Last updated: 14 July 2026** | [Report an issue](https://github.com/Supersynergy/awesome-ai-agents-2025/issues) | [Request an addition](https://github.com/Supersynergy/awesome-ai-agents-2025/issues/new)
