# Awesome Lists and Comparison Sources

This file is the cross-list index for the current README. It was checked on **2 August 2026** with Superweb, ghmax, GitHub metadata, and a read-only PUM refresh. Use it for recall; verify current status in the upstream repository before adopting a tool.

The local project is branded **Awesome AI Agents**. The previous dated checkout name is intentionally removed from the maintained surface; historical dates remain only where they describe a source or release.

## Current comparison lists

| Repository | Focus | Freshness signal observed |
|------------|-------|----------------------------|
| [e2b-dev/awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents) | Broad open-source and hosted AI-agent directory | 29.2K stars; pushed 9 Jul 2026 |
| [caramaschiHG/awesome-ai-agents-2026](https://github.com/caramaschiHG/awesome-ai-agents-2026) | Broad 2026 catalog and category recall | 1.5K stars; pushed 10 Jun 2026; updated 1 Aug |
| [Zijian-Ni/awesome-ai-agents-2026](https://github.com/Zijian-Ni/awesome-ai-agents-2026) | Foundation models, agent protocols, coding agents, security | 212 stars; pushed 1 Aug 2026 |
| [ARUNAGIRINATHAN-K/awesome-ai-agents-2026](https://github.com/ARUNAGIRINATHAN-K/awesome-ai-agents-2026) | Broad stack with security, observability, and deployment lanes | 281 stars; pushed 30 Jul 2026 |
| [Deep-Insight-Labs/awesome-ai-agents](https://github.com/Deep-Insight-Labs/awesome-ai-agents) | Frameworks, observability, and emerging projects | 37 stars; pushed 28 Apr 2026 |
| [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) | Claude Code skills, plugins, agents, and tooling | 51.5K stars; pushed 1 Aug 2026 |
| [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | MCP server discovery | 91.7K stars; pushed 29 Jul 2026 |
| [mcp-security-project/awesome-agentic-mcp-security](https://github.com/mcp-security-project/awesome-agentic-mcp-security) | MCP and agentic security research, tooling, labs, and advisories | 19 stars; pushed 14 Jul 2026 |
| [e2b-dev/awesome-ai-sdks](https://github.com/e2b-dev/awesome-ai-sdks) | SDKs and building blocks for agent applications | 1.2K stars; pushed 9 Jul 2026 |
| [bradAGI/awesome-cli-coding-agents](https://github.com/bradAGI/awesome-cli-coding-agents) | Terminal-native coding agents, harnesses, runners, and infrastructure | 919 stars; pushed 1 Aug 2026 |
| [sammcj/agentic-coding](https://github.com/sammcj/agentic-coding) | Agentic coding rules, templates, and workflow guidance | 154 stars; pushed 30 Jul 2026 |
| [mokevnin/agentic-coding-design-patterns](https://github.com/mokevnin/agentic-coding-design-patterns) | Agentic software-development patterns | 76 stars; pushed 31 Jul 2026 |

## What the comparison pass found

- **Coding agents are now a separate lane:** Codex, OpenCode, Claude Code, Gemini CLI, Cline, OpenHands, Aider, and Kimi CLI should not be buried under generic frameworks.
- **MCP and A2A are distinct:** MCP connects agents to tools and data; A2A connects agents to agents.
- **Typed SDKs are a strong current category:** OpenAI Agents SDK, Claude Agent SDK, Google ADK, Pydantic AI, Mastra, smolagents, Agno, and `mcp-agent` all have clear upstream homes.
- **Runtime and control-plane projects are separating from frameworks:** OpenShell, Docker Agent, Archestra, Kun, herdr, and Mission Control target execution, governance, fleet operations, or workspace management rather than only prompt composition.
- **Security deserves its own source lane:** `awesome-agentic-mcp-security` and Snyk Agent Scan add threat research and component scanning that a general agent list cannot summarize safely.
- **Freshness needs explicit flags:** comparison lists contain archived, unverified, stale, or promotional entries. This repository keeps those out of the core snapshot unless independently verified.
- **YouTube is discovery only:** current videos repeatedly discuss agentic coding workflows, MCP versus APIs/skills, and local coding setups. Video popularity is not an inclusion criterion.

## Discovery and context sources

| Source | Role | Safe interpretation |
|---|---|---|
| [GitStars.io trending API](https://gitstars.io/api/trending) via `ghmax --gitstars` | Star-velocity and momentum discovery | Strong candidate signal; noisy feed, never a quality score |
| GitStars.io name index via `ghmax --gitstars-suggest` | Name-based recall for `ai`, `agentic`, `coding agent`, `mcp`, `runtime`, `skills`, and related lanes | API caps each query at 10 rows; use it to find candidates, then verify upstream |
| Tool Radar (`/Users/master/BASE/projects/awesome-indexer`) | Local Gitstars/ghmax/DuckLake ranking and feature map | Use ranked snapshot plus upstream verification |
| Superweb CLI (`superweb`) | Current web search and primary-source retrieval | Search accelerator; source page remains evidence |
| [Synapse](https://github.com/Supersynergy/synapse-memory) | Local cited memory and bounded context packs | Context layer, not a public popularity metric |
| PUM (`pum refresh --json`) | Host/package freshness and source coverage | Read-only tool inventory; not repository quality evidence |

## Official protocol and ecosystem sources

| Source | Purpose |
|--------|---------|
| [MCP specification](https://modelcontextprotocol.io/specification/latest) | Protocol definition and transport semantics |
| [MCP servers](https://github.com/modelcontextprotocol/servers) | Reference servers and examples |
| [A2A protocol](https://a2a-protocol.org/latest/) | Agent-to-agent interoperability |
| [OpenTelemetry](https://opentelemetry.io/) | Vendor-neutral traces, metrics, and logs |
| [SWE-bench](https://github.com/SWE-bench/SWE-bench) | Software-engineering agent evaluation |
| [Hugging Face Agents course](https://huggingface.co/learn/agents-course) | Agent concepts and practical exercises |

For the latest capability synthesis, see the [2 August update audit](docs/UPDATE-2026-08-02.md) and the earlier [frontier breakthroughs](docs/FRONTIER-BREAKTHROUGHS-2026-07-14.md).

## Selection checklist

Before copying an entry into an awesome list, check:

1. Official upstream or documentation URL.
2. Active repository and non-archived status.
3. One concrete capability and target use case.
4. License and deployment model.
5. Security boundary, especially for tools, browser control, code execution, and MCP servers.
6. Date for any version, pricing, benchmark, or adoption claim.

## Audit trail

See [docs/UPDATE-2026-08-02.md](docs/UPDATE-2026-08-02.md) for the exact Superweb, ghmax, PUM, and GitHub metadata snapshot. The [July gap audit](docs/GAP-AUDIT-2026-07-14.md) remains historical context for Synapse, ZeroClaw, ACP, and skills.

**Last updated: 2 August 2026**
