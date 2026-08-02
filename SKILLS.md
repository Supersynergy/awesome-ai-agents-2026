# Agent Skills Catalog

> **Freshness boundary: 2 August 2026.** This catalog records the current GitStars.io `skills` name-index results and the skill catalogs already found during the Superweb/GitHub audit. Stars are discovery signals, not quality or safety scores.

Agent skills are executable instructions, plugins, or capability catalogs. Read the upstream `SKILL.md`, plugin manifest, permissions, and install instructions before enabling them. This list does not imply endorsement of every contained skill.

## GitStars.io skill index

The ten rows below are the complete result of the bounded `ghmax --gitstars-suggest skills` query on 2 August 2026. All repositories were checked against live GitHub metadata: active, non-fork, and non-archived at the snapshot.

| Catalog | Stars | Pushed | License metadata | Focus | Install path |
|---|---:|---|---|---|---|
| [trailofbits/skills](https://github.com/trailofbits/skills) | 6.4K | 1 Aug | CC-BY-SA-4.0 | Security research, vulnerability detection, code auditing, malware analysis, and verification plugins | `codex plugin marketplace add trailofbits/skills` |
| [dotnet/skills](https://github.com/dotnet/skills) | 4.8K | 1 Aug | MIT | .NET, C#, MSBuild, NuGet, testing, .NET AI, RAG, agent workflows, and MCP | `codex plugin marketplace add dotnet/skills` |
| [NVIDIA/skills](https://github.com/NVIDIA/skills) | 2.8K | 1 Aug | Apache-2.0 + CC-BY-4.0 | Physical AI, robotics, simulation, CUDA, RAG, and NVIDIA platform workflows | `npx skills add nvidia/skills` |
| [davidondrej/skills](https://github.com/davidondrej/skills) | 2.7K | 1 Aug | MIT | General coding, research, orchestration, skill authoring, documentation, and operations | See upstream installation instructions |
| [jakubkrehel/skills](https://github.com/jakubkrehel/skills) | 2.6K | 29 Jul | MIT | Interface review, UI polish, typography, color, layout, accessibility, and UX writing | `npx skills add jakubkrehel/skills` |
| [BankrBot/skills](https://github.com/BankrBot/skills) | 1.2K | 1 Aug | Not declared in GitHub metadata | Web3, DeFi, wallets, on-chain data, payments, and agent commerce | Provider-specific install; inspect each skill before use |
| [chrisbanes/skills](https://github.com/chrisbanes/skills) | 879 | 1 Aug | Apache-2.0 | Kotlin, Jetpack Compose, Android state, performance, testing, and workflows | `npx skills add chrisbanes/skills` |
| [dzhng/skills](https://github.com/dzhng/skills) | 628 | 1 Aug | MIT | Domain-agnostic software-factory skills for planning, building, review, visual work, and verification | `npx skills add dzhng/skills` |
| [pedronauck/skills](https://github.com/pedronauck/skills) | 548 | 1 Aug | Not declared in GitHub metadata | 132 skills across engineering, curated community, marketing, business, and general workflows | `npx skills add https://github.com/pedronauck/skills` |
| [social-media-skills/skills](https://github.com/social-media-skills/skills) | 10 | 30 Jul | MIT | 106 social-media skills for strategy, writing, video, design, growth, publishing, and analytics | `npx skills add social-media-skills/skills` |

## Other verified skill sources

These were found in the earlier comparison and primary-source pass rather than the ten-row GitStars name query.

| Catalog | Focus | Install path |
|---|---|---|
| [AWS Agent Toolkit for AWS](https://github.com/aws/agent-toolkit-for-aws) | AWS MCP servers, plugins, skills, and guardrails for coding agents | `npx skills add aws/agent-toolkit-for-aws/skills` |
| [Vercel AI SDK skills](https://github.com/vercel/ai) | Skill for building with the TypeScript AI SDK and its agent/tool-loop APIs | `npx skills add vercel/ai` |
| [Superpowers](https://github.com/obra/superpowers) | Agent skills framework and software-development methodology | See upstream installation instructions |
| [Understand-Anything](https://github.com/Egonex-AI/Understand-Anything) | Codebase knowledge graph and repository understanding for coding agents | See upstream installation instructions |

## Safety boundaries

- Treat every skill as executable agent authority. Review its instructions, scripts, network calls, file access, and secret handling before installation.
- Bankr skills can reach wallets, DeFi protocols, payments, and on-chain execution. Use read-only discovery first, explicit transaction previews, scoped keys, and human approval for every irreversible action.
- Social-media skills can prepare or publish content. Keep publishing behind an explicit user confirmation and a final preview.
- Vendor and language catalogs are useful when the task matches their domain. Do not load all catalogs into every agent context.
- Current stars, a recent push, and a valid license do not prove correctness, security, or production readiness.

## Audit source

- GitStars discovery: `ghmax --gitstars-suggest skills --gitstars-no-lake --no-cache --format tsv`
- Official README checks: Superweb fetches from each upstream repository
- Live metadata: GitHub repository API, checked 2 August 2026
- Detailed decision trail: [docs/UPDATE-2026-08-02.md](docs/UPDATE-2026-08-02.md)

**Last updated: 2 August 2026**
