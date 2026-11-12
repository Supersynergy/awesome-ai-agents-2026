# Agent frameworks: a decision guide

**Checked 13 October 2026** · [Main index](../README.md) · [Harness research](HARNESS-RESEARCH.md)

Choose a framework by the state, tools and failure recovery your application needs. The shortlist below links to current upstream projects; it is not a performance or production-readiness ranking.

## Current shortlist

| Framework | Best fit |
|---|---|
| [LangGraph](https://github.com/langchain-ai/langgraph) | Stateful execution with recovery and human intervention |
| [Deep Agents](https://github.com/langchain-ai/deepagents) | Planning harness with files and subagents |
| [Microsoft Agent Framework](https://github.com/microsoft/agent-framework) | Python/.NET agents and multi-agent workflows |
| [CrewAI](https://github.com/crewAIInc/crewAI) | Role-based agents and coordinated workflows |
| [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) | Tool-using agents with handoffs and tracing |
| [Claude Agent SDK for Python](https://github.com/anthropics/claude-agent-sdk-python) | Building around Claude Code primitives and tool use |
| [Google ADK](https://github.com/google/adk-python) | Code-first agents in the Google ecosystem |
| [Pydantic AI](https://github.com/pydantic/pydantic-ai) | Type-safe agents and validated structured output |
| [Mastra](https://github.com/mastra-ai/mastra) | TypeScript agents and workflows |
| [Vercel AI SDK](https://github.com/vercel/ai) | Provider-agnostic TypeScript toolkit for applications and tool-loop agents |
| [CopilotKit](https://github.com/CopilotKit/CopilotKit) | Agent interfaces with shared state and approval flows |
| [Stately Agent](https://github.com/statelyai/agent) | State-machine-controlled LLM agents |
| [Workflow SDK](https://github.com/vercel/workflow) | Durable TypeScript workflows |
| [smolagents](https://github.com/huggingface/smolagents) | Small code-first agents and `CodeAgent` workflows |
| [Agno](https://github.com/agno-agi/agno) | Model-agnostic agents with tool access |
| [mcp-agent](https://github.com/lastmile-ai/mcp-agent) | MCP-native agents and compact workflow patterns |
| [Vercel Eve](https://github.com/vercel/eve) | Filesystem-oriented agent framework |
| [Omnigent](https://github.com/omnigent-ai/omnigent) | Meta-harness for interoperable coding agents and policy controls |
| [Open Multi-Agent](https://github.com/open-multi-agent/open-multi-agent) | TypeScript orchestration with runtime-planned task DAGs |
| [Archestra](https://github.com/archestra-ai/archestra) | MCP/A2A access gateway and orchestration |

## Match the architecture to the job

| Requirement | Starting points | Acceptance to define |
|---|---|---|
| A small tool-using agent | OpenAI Agents SDK, Pydantic AI, smolagents | Validated tool input, explicit failures and a bounded task |
| Durable execution with interruptions | LangGraph, Workflow SDK | A stopped run resumes from persisted state without repeating effects |
| A prebuilt planning harness | Deep Agents, Claude Agent SDK | File and tool scopes, delegated state and a task verifier |
| Python/.NET workflows | Microsoft Agent Framework | Provider compatibility, state ownership and migration behavior |
| TypeScript application and UI | AI SDK, Mastra, CopilotKit | Streaming behavior, user approval and persisted application state |
| Coordinated workers | CrewAI, Open Multi-Agent | Exclusive ownership, bounded workers and integrated output |
| MCP access and governance | mcp-agent, Archestra | Authentication, allowlists, timeouts and audited tool calls |

Read the current upstream quickstart before installing. Pin the package or commit used in an evaluation and record the resolved provider and model. Examples from one release should not be assumed compatible with another.

## Evaluate a candidate

1. Run one representative task with an external checker.
2. Exercise a tool failure, timeout and interruption.
3. Inspect state persistence and the boundary around secrets and tool execution.
4. Record total effort through verified completion, including retries and review.
5. Add orchestration only when it resolves an observed failure or bottleneck.

[GitHub metadata](data/catalog-2026-10-13.json) records archive status, revisions and published release fields. Those fields establish repository state; they do not prove application behavior.
