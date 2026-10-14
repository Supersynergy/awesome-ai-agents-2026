# Agent skills catalog

**Checked 13 October 2026** · [Main index](README.md) · [Update audit](docs/UPDATE-2026-10-13.md)

Skills supply task-specific instructions and sometimes scripts or plugins. Use the upstream installation guide and inspect the exact skill before enabling it. A repository-wide listing does not endorse every instruction it contains.

## Current catalogs

| Project | Role |
|---|---|
| [OpenAI Skills](https://github.com/openai/skills) | Codex skill catalog; inspect each skill's instructions and permissions |
| [Superpowers](https://github.com/obra/superpowers) | Agentic skills framework and software-development methodology |
| [Understand-Anything](https://github.com/Egonex-AI/Understand-Anything) | Interactive codebase knowledge graph for Claude Code, Codex, Cursor, Copilot, and Gemini CLI |
| [AGENTS.md](https://github.com/agentsmd/agents.md) | Keep project-specific constraints, workflows, and safety context close to the repository |
| [NVIDIA Agent Skills](https://github.com/NVIDIA/skills) | Skills for NVIDIA platform and robotics workflows |
| [Trail of Bits Skills](https://github.com/trailofbits/skills) | Security research and verification for coding agents |
| [AWS Agent Toolkit](https://github.com/aws/agent-toolkit-for-aws) | AWS tools and skills for coding agents |
| [AWS MCP servers](https://github.com/awslabs/mcp) | AWS-focused MCP server collection; the upstream README points new work to Agent Toolkit for AWS |
| [.NET Agent Skills](https://github.com/dotnet/skills) | .NET/C# development and agent workflows |
| [David Ondrej Skills](https://github.com/davidondrej/skills) | General engineering and research skills |
| [Interfaces Skills](https://github.com/jakubkrehel/skills) | Interface design and accessibility skills |
| [Bankr Skills](https://github.com/BankrBot/skills) | On-chain workflows; transactions need approval |
| [Chris Banes Skills](https://github.com/chrisbanes/skills) | Kotlin and Android development skills |
| [dzhng Skills](https://github.com/dzhng/skills) | Planning and engineering workflows |
| [Pedro Nauck Skills](https://github.com/pedronauck/skills) | Engineering and business skill catalog |
| [Social Media Skills](https://github.com/social-media-skills/skills) | Social-media workflows; publishing needs approval |
| [Aident Loadout](https://github.com/Aident-AI/aident-skill) | Connect Codex, Claude Code, Cursor and other MCP clients to 1,000+ apps and 400+ Skills through one reusable setup |


## Choose and verify a skill

- Match one concrete task to a skill's documented scope.
- Read its instructions, scripts, network calls and requested permissions.
- Verify the source revision and component license before copying or installing.
- Define the expected output and an executable acceptance check where possible.
- Keep publication, payments and other irreversible effects behind the required user authority.
- Load detailed references when needed rather than placing every catalog in the agent context.

The [metadata snapshot](docs/data/catalog-2026-10-13.json) contains current repository and license fields. Missing license metadata stays unknown; a detected top-level license does not establish the license of every included file.
