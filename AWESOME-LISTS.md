# Awesome Lists and Comparison Sources

This file is the cross-list index for the current README. It was checked on **14 July 2026**. Use it for recall; verify current status in the upstream repository before adopting a tool.

## Current comparison lists

| Repository | Focus | Freshness signal observed |
|------------|-------|----------------------------|
| [e2b-dev/awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents) | Broad open-source and hosted AI-agent directory | HEAD `999f3c3`, 9 Jul 2026 |
| [caramaschiHG/awesome-ai-agents-2026](https://github.com/caramaschiHG/awesome-ai-agents-2026) | Broad 2026 catalog and category recall | HEAD `781b695`, 2 Apr 2026 |
| [Zijian-Ni/awesome-ai-agents-2026](https://github.com/Zijian-Ni/awesome-ai-agents-2026) | Foundation models, agent protocols, coding agents, security | HEAD `facfe2c`, 2 Jul 2026 |
| [Deep-Insight-Labs/awesome-ai-agents](https://github.com/Deep-Insight-Labs/awesome-ai-agents) | Frameworks, observability, and emerging projects | HEAD `a4b4fa0`, 28 Apr 2026 |
| [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | Claude Code skills, plugins, agents, and tooling | HEAD `36ba8e2`, 14 Jul 2026 |
| [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | MCP server discovery | Live metadata checked 13 Jul 2026 |
| [e2b-dev/awesome-sdks-for-ai-agents](https://github.com/e2b-dev/awesome-sdks-for-ai-agents) | SDKs and building blocks for agent applications | Companion list to E2B's agent directory |

## What the comparison pass found

- **Coding agents are now a separate lane:** Codex, OpenCode, Claude Code, Gemini CLI, Cline, OpenHands, Aider, and Kimi CLI should not be buried under generic frameworks.
- **MCP and A2A are distinct:** MCP connects agents to tools and data; A2A connects agents to agents.
- **Typed SDKs are a strong current category:** OpenAI Agents SDK, Claude Agent SDK, Google ADK, Pydantic AI, Mastra, smolagents, Agno, and `mcp-agent` all have clear upstream homes.
- **Freshness needs explicit flags:** comparison lists contain archived, unverified, stale, or promotional entries. This repository keeps those out of the core snapshot unless independently verified.
- **YouTube is discovery only:** current videos repeatedly discuss agentic coding workflows, MCP versus APIs/skills, and local coding setups. Video popularity is not an inclusion criterion.

## Official protocol and ecosystem sources

| Source | Purpose |
|--------|---------|
| [MCP specification](https://modelcontextprotocol.io/specification/latest) | Protocol definition and transport semantics |
| [MCP servers](https://github.com/modelcontextprotocol/servers) | Reference servers and examples |
| [A2A protocol](https://a2a-protocol.org/latest/) | Agent-to-agent interoperability |
| [OpenTelemetry](https://opentelemetry.io/) | Vendor-neutral traces, metrics, and logs |
| [SWE-bench](https://github.com/SWE-bench/SWE-bench) | Software-engineering agent evaluation |
| [Hugging Face Agents course](https://huggingface.co/learn/agents-course) | Agent concepts and practical exercises |

## Selection checklist

Before copying an entry into an awesome list, check:

1. Official upstream or documentation URL.
2. Active repository and non-archived status.
3. One concrete capability and target use case.
4. License and deployment model.
5. Security boundary, especially for tools, browser control, code execution, and MCP servers.
6. Date for any version, pricing, benchmark, or adoption claim.

## Audit trail

See [docs/UPDATE-2026-07-14.md](docs/UPDATE-2026-07-14.md) for the exact comparison commits, Tool Radar run, Superweb retrieval, GitHub metadata snapshot, and YouTube fallback limits.

**Last updated: 14 July 2026**
