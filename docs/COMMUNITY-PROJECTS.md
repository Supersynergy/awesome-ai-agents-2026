# Community agent runtimes and workspaces

**Checked 13 October 2026** · [Main index](../README.md) · [Harness research](HARNESS-RESEARCH.md)

These projects provide execution environments, personal assistants and operations tools. The descriptions summarize upstream scope; this update did not run their software or verify deployments.

| Runtime | Delivery | Use case |
|---|---|---|
| [OpenClaw](https://github.com/openclaw/openclaw) | Self-hosted | Personal assistants across channels with tools and memory |
| [Goose](https://github.com/aaif-goose/goose) | Local / self-hosted | Extensible agent with MCP and any-LLM support |
| [OpenHands](https://github.com/OpenHands/OpenHands) | Open source | Software-development agents and sandboxed execution |
| [NVIDIA OpenShell](https://github.com/NVIDIA/OpenShell) | Self-hosted | Policy-governed private sandboxes for autonomous agents |
| [Docker Agent](https://github.com/docker/docker-agent) | Docker Desktop / self-hosted | Declarative YAML agents with MCP tools |
| [Kun](https://github.com/KunAgent/Kun) | Local-first | Desktop/TUI workspace for agent tasks |
| [Mission Control](https://github.com/builderz-labs/mission-control) | Self-hosted | Dispatch and operations across agent runtimes |
| [Autonomous OS](https://github.com/autonomous-ai/Physical-AI-Operating-System) | Edge / self-hosted | Physical-AI operating system with swappable agent runtimes and deterministic safety bounds |
| [AgenticROS](https://github.com/agenticros/agenticros) | ROS 2 / self-hosted | Robot tools with MCP adapters |
| [OpenAI Deep Research](https://openai.com/index/introducing-deep-research/) | Hosted | Long-running, citation-oriented research |
| [Gemini Deep Research](https://gemini.google.com/) | Hosted | Research tasks in the Google ecosystem |
| [Manus](https://manus.im/) | Hosted | General-purpose autonomous task execution |
| [Replit Agent](https://replit.com/ai) | Hosted | Build and deploy applications from natural language |
| [v0](https://v0.dev/) | Hosted | UI and application generation |
| [Lovable](https://lovable.dev/) | Hosted | Product-oriented application prototyping |

### Lightweight and always-on runtimes

Repository metadata checked **13 October 2026**. Language and design goals describe upstream projects; hardware footprint and reliability require workload measurements.

| Runtime | Language / shape | Best fit |
|---|---|---|
| [Hermes Agent](https://github.com/NousResearch/hermes-agent) | Python / local agent | Persistent personal workflows with skills |
| [nanobot](https://github.com/HKUDS/nanobot) | Python / lightweight | Small agent for chat and tool use |
| [ZeroClaw](https://github.com/zeroclaw-labs/zeroclaw) | Rust / single binary | Rust assistant runtime with policy controls |
| [NanoClaw](https://github.com/nanocoai/nanoclaw) | TypeScript / containers | OpenClaw-like channels with container isolation and memory |
| [PicoClaw](https://github.com/sipeed/picoclaw) | Go / tiny runtime | Small hardware and deploy-anywhere assistant scenarios |
| [IronClaw](https://github.com/nearai/ironclaw) | Rust / Agent OS | Rust assistant runtime with a security focus |
| [NullClaw](https://github.com/nullclaw/nullclaw) | Zig / minimal runtime | Small autonomous assistant infrastructure |

### New runtime, control-plane, and physical-agent candidates

Additional execution surfaces for fleet operations, shared workspaces and physical systems. Repository status is recorded in the [October snapshot](data/catalog-2026-10-13.json).

| Project | Shape | Best fit |
|---|---|---|
| [herdr](https://github.com/herdrdev/herdr) | Rust / terminal runtime | Workspaces and lifecycle management for coding-agent fleets |
| [holaOS](https://github.com/holaboss-ai/holaOS) | TypeScript / agent workspace | Shared context and MCP across applications |
| [Archestra](https://github.com/archestra-ai/archestra) | TypeScript / gateway | Controlled enterprise access to MCP and A2A |
| [Open Multi-Agent](https://github.com/open-multi-agent/open-multi-agent) | TypeScript / orchestrator | Dynamic multi-agent workflows in a Node.js application |
| [Wippy](https://github.com/wippyai/runtime) | Go / Lua-WASM runtime | Durable actor runtime with policy controls |
| [AgenticFlowX](https://github.com/AgenticFlowX/agenticflowx) | VS Code / workflow layer | VS Code agent workflows with repository traceability |

## Reproduce a useful workflow

Start from an upstream example at a pinned revision. Use synthetic inputs and scoped credentials, then check the actual output, restart behavior and failure path. For coding work, give the agent an isolated checkout and keep acceptance checks outside its write access.

The former guide's placeholder repositories and unverified tutorial deployments have been removed. Real upstream examples belong with their project, revision and observed result.
