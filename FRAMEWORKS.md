# AI Agent Frameworks - Detailed Guide

> **Freshness note (2 August 2026):** The detailed examples below are a legacy deep guide with versioned snippets. Use the [current README](README.md) and [update audit](docs/UPDATE-2026-08-02.md) for the maintained inventory and current shortlist.

A comprehensive breakdown of frameworks for building local AI agents, including features, use cases, installation, and examples.

## Table of Contents

- [Current 2026 Shortlist](#current-2026-shortlist)
- [Tier 1: Production-Ready](#tier-1-production-ready)
- [Tier 2: Specialized](#tier-2-specialized)
- [Tier 3: Emerging](#tier-3-emerging)
- [Framework Comparison Matrix](#framework-comparison-matrix)
- [Choosing the Right Framework](#choosing-the-right-framework)

---

## Current 2026 Shortlist

The maintained shortlist is intentionally smaller than this historical guide. Verify versions and provider support upstream before installing.

| Framework | Current signal | Best fit |
|---|---:|---|
| [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) | 28.3K stars | Tools, handoffs, tracing, and sandboxed agent work |
| [Google ADK](https://github.com/google/adk-python) | 21.0K stars | Code-first agents, evaluation, and Google deployment |
| [Pydantic AI](https://github.com/pydantic/pydantic-ai) | 19.0K stars | Typed tool I/O and validated structured output |
| [Mastra](https://github.com/mastra-ai/mastra) | 26.8K stars | TypeScript workflows, memory, and observability |
| [Vercel Eve](https://github.com/vercel/eve) | 4.2K stars | Filesystem-first durable agents; beta |
| [Omnigent](https://github.com/omnigent-ai/omnigent) | 8.0K stars | Interoperable coding-agent harnesses and policy controls |
| [Open Multi-Agent](https://github.com/open-multi-agent/open-multi-agent) | 6.7K stars | Dynamic multi-agent task graphs in TypeScript |
| [Archestra](https://github.com/archestra-ai/archestra) | 4.1K stars | MCP/A2A gateway, registry, orchestration, and guardrails |

---

## Tier 1: Production-Ready

These frameworks are mature, well-documented, and suitable for production deployments.

### LangChain

**The Swiss Army Knife of Agent Frameworks**

- **GitHub**: [langchain-ai/langchain](https://github.com/langchain-ai/langchain)
- **Stars**: 116,000+
- **Language**: Python, JavaScript/TypeScript
- **License**: MIT

#### Overview

LangChain is the most widely adopted framework for building LLM-powered applications. It provides a modular approach to constructing AI agents, allowing developers to chain LLMs with external tools, memory modules, and APIs.

#### Key Features

- **Modular architecture** - Mix and match components
- **Extensive integrations** - 100+ tool and service integrations
- **Memory systems** - Multiple memory types for context management
- **Streaming support** - Real-time response streaming
- **Callbacks** - Comprehensive logging and monitoring
- **Production tools** - LangSmith for observability, LangServe for deployment

#### Best For

- Complex, multi-step workflows
- Applications requiring many integrations
- Teams needing production observability
- Both experimentation and production

#### Installation

```bash
pip install langchain langchain-community langchain-ollama
```

#### Example: Research Agent

```python
from langchain_ollama import OllamaLLM
from langchain.agents import create_react_agent, AgentExecutor
from langchain.tools import DuckDuckGoSearchRun
from langchain.prompts import PromptTemplate

# Initialize local LLM
llm = OllamaLLM(model="llama3.1:8b")

# Set up tools
search = DuckDuckGoSearchRun()
tools = [search]

# Create agent prompt
template = """Answer the following questions as best you can.

You have access to the following tools:
{tools}

Use the following format:
Question: the input question
Thought: think about what to do
Action: the action to take, one of [{tool_names}]
Action Input: the input to the action
Observation: the result of the action
... (repeat as needed)
Final Answer: the final answer

Question: {input}
{agent_scratchpad}"""

prompt = PromptTemplate.from_template(template)

# Create and run agent
agent = create_react_agent(llm, tools, prompt)
executor = AgentExecutor(agent=agent, tools=tools, verbose=True)
result = executor.invoke({"input": "What are the benefits of local AI agents?"})
```

#### Limitations

- Steep learning curve for beginners
- Can be verbose for simple tasks
- Frequent API changes between versions

---

### LangGraph

**Graph-Based Agent Orchestration**

- **GitHub**: [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph)
- **Stars**: 19,000+
- **Language**: Python
- **License**: MIT

#### Overview

LangGraph extends LangChain with graph-based state management for building complex, stateful multi-agent applications. It provides explicit control flow through nodes and edges.

#### Key Features

- **Graph-based architecture** - Visual workflow design
- **State management** - Built-in state persistence
- **Checkpointing** - Save and resume workflows
- **Human-in-the-loop** - Pause for human approval
- **Streaming** - Stream both tokens and intermediate steps
- **Cycles and branches** - Complex control flow patterns

#### Best For

- Complex workflows requiring explicit control flow
- Applications needing audit trails
- Processes with human approval steps
- Long-running, resumable tasks

#### Installation

```bash
pip install langgraph langchain-ollama
```

#### Example: Multi-Step Research Workflow

```python
from langgraph.graph import StateGraph, END
from typing import TypedDict, List
from langchain_ollama import OllamaLLM

class ResearchState(TypedDict):
    topic: str
    sources: List[str]
    summary: str
    final_report: str

llm = OllamaLLM(model="llama3.1:8b")

def research_topic(state: ResearchState) -> ResearchState:
    # Simulate research
    state["sources"] = ["Source 1", "Source 2", "Source 3"]
    return state

def summarize_findings(state: ResearchState) -> ResearchState:
    prompt = f"Summarize research on {state['topic']}"
    state["summary"] = llm.invoke(prompt)
    return state

def write_report(state: ResearchState) -> ResearchState:
    prompt = f"Write a report based on: {state['summary']}"
    state["final_report"] = llm.invoke(prompt)
    return state

# Build graph
workflow = StateGraph(ResearchState)
workflow.add_node("research", research_topic)
workflow.add_node("summarize", summarize_findings)
workflow.add_node("report", write_report)

workflow.set_entry_point("research")
workflow.add_edge("research", "summarize")
workflow.add_edge("summarize", "report")
workflow.add_edge("report", END)

# Compile and run
app = workflow.compile()
result = app.invoke({"topic": "local AI agents"})
```

#### Limitations

- Requires understanding of graph concepts
- More complex setup than simple agents
- Tightly coupled with LangChain ecosystem

---

### CrewAI

**Role-Based Multi-Agent Collaboration**

- **GitHub**: [crewAIInc/crewAI](https://github.com/crewAIInc/crewAI)
- **Stars**: 38,000+
- **Language**: Python
- **License**: MIT

#### Overview

CrewAI simplifies building collaborative AI systems by organizing agents into "crews" with defined roles, goals, and workflows. It mimics human team structures to solve complex problems.

#### Key Features

- **Role-based agents** - Clear responsibilities and expertise
- **Task delegation** - Automatic work distribution
- **Sequential and parallel** - Flexible task execution
- **Memory sharing** - Agents learn from each other
- **Tool integration** - Built-in and custom tools
- **Process management** - Sequential, hierarchical, or parallel

#### Best For

- Team-like collaborative tasks
- Rapid prototyping of multi-agent systems
- Tasks with clear role definitions
- Users wanting simple multi-agent setup

#### Installation

```bash
pip install crewai crewai-tools langchain-ollama
```

#### Example: Content Creation Crew

```python
from crewai import Agent, Task, Crew, Process
from langchain_ollama import OllamaLLM

llm = OllamaLLM(model="llama3.1:8b")

# Define agents
researcher = Agent(
    role="Research Analyst",
    goal="Find comprehensive information on topics",
    backstory="Expert at gathering and analyzing information",
    llm=llm,
    verbose=True
)

writer = Agent(
    role="Content Writer",
    goal="Create engaging, well-structured content",
    backstory="Experienced writer with clear communication skills",
    llm=llm,
    verbose=True
)

editor = Agent(
    role="Editor",
    goal="Ensure content is polished and error-free",
    backstory="Meticulous editor with high standards",
    llm=llm,
    verbose=True
)

# Define tasks
research_task = Task(
    description="Research local AI agents and their benefits",
    expected_output="Comprehensive research notes with key points",
    agent=researcher
)

writing_task = Task(
    description="Write a blog post about local AI agents",
    expected_output="Engaging blog post, 500-800 words",
    agent=writer
)

editing_task = Task(
    description="Edit and polish the blog post",
    expected_output="Final polished blog post",
    agent=editor
)

# Create crew
crew = Crew(
    agents=[researcher, writer, editor],
    tasks=[research_task, writing_task, editing_task],
    process=Process.sequential,
    verbose=True
)

# Run
result = crew.kickoff()
print(result)
```

#### Limitations

- Less flexible than LangChain for custom workflows
- Role abstraction may not fit all use cases
- Limited control over inter-agent communication

---

### AutoGen (AG2)

**Microsoft's Multi-Agent Conversation Framework**

- **GitHub**: [microsoft/autogen](https://github.com/microsoft/autogen)
- **Stars**: 50,000+
- **Language**: Python
- **License**: MIT

#### Overview

AutoGen is Microsoft's open-source framework for building multi-agent systems through conversational interactions. Version 0.4 (released January 2025) brought a complete redesign with async, event-driven architecture.

#### Key Features

- **Conversational agents** - Natural dialogue-based collaboration
- **Code execution** - Built-in sandboxed code running
- **Human-in-the-loop** - Easy human participation
- **Flexible conversations** - Group chats, nested conversations
- **Async architecture** - Event-driven design in v0.4
- **Observability** - Strong logging and tracing

#### Best For

- Research and academic prototyping
- Code-heavy workflows
- Microsoft ecosystem integration
- Complex multi-agent conversations

#### Installation

```bash
pip install autogen-agentchat
```

#### Example: Coding Assistant Duo

```python
import autogen

# Configure for local model
config_list = [{
    "model": "llama3.1:8b",
    "base_url": "http://localhost:11434/v1",  # Ollama
    "api_key": "ollama"
}]

llm_config = {
    "config_list": config_list,
    "temperature": 0.7
}

# Create assistant agent
assistant = autogen.AssistantAgent(
    name="coding_assistant",
    system_message="You are a helpful coding assistant.",
    llm_config=llm_config
)

# Create user proxy
user_proxy = autogen.UserProxyAgent(
    name="user",
    human_input_mode="NEVER",
    max_consecutive_auto_reply=5,
    code_execution_config={
        "work_dir": "coding_output",
        "use_docker": False
    }
)

# Start conversation
user_proxy.initiate_chat(
    assistant,
    message="Write a Python function to calculate fibonacci numbers"
)
```

#### Limitations

- More complex setup than CrewAI
- Breaking changes in v0.4 migration
- Requires understanding of conversation patterns

---

## Tier 2: Specialized

These frameworks excel in specific use cases or have unique capabilities.

### AutoGPT

**The Original Autonomous Agent**

- **GitHub**: [Significant-Gravitas/AutoGPT](https://github.com/Significant-Gravitas/AutoGPT)
- **Stars**: 170,000+
- **Language**: Python
- **License**: MIT

#### Overview

AutoGPT pioneered the concept of fully autonomous AI agents that can plan and execute tasks with minimal human intervention. It chains LLM calls to accomplish complex goals.

#### Key Features

- **Goal-driven autonomy** - Give it a goal, it figures out the steps
- **Self-planning** - Breaks tasks into subtasks automatically
- **Memory management** - Short and long-term memory
- **Web browsing** - Built-in web interaction
- **File management** - Create, read, and modify files
- **Plugin system** - Extensible capabilities

#### Best For

- Fully autonomous task execution
- Users who prefer minimal intervention
- Experimental projects
- Learning about autonomous systems

#### Installation

```bash
git clone https://github.com/Significant-Gravitas/AutoGPT.git
cd AutoGPT
pip install -r requirements.txt
```

#### Configuration for Local LLM

```yaml
# .env or config file
SMART_LLM=ollama/llama3.1:8b
FAST_LLM=ollama/llama3.1:8b
EMBEDDING_MODEL=ollama/nomic-embed-text
```

#### Limitations

- Can be unpredictable
- Token-heavy due to planning overhead
- Requires careful goal specification

---

### Open Interpreter

**Natural Language Code Execution**

- **GitHub**: [openinterpreter/openinterpreter](https://github.com/openinterpreter/openinterpreter)
- **Stars**: 56,000+
- **Language**: Python
- **License**: AGPL-3.0

#### Overview

Open Interpreter lets LLMs run code on your computer. It provides a ChatGPT-like interface that can execute Python, JavaScript, shell commands, and more.

#### Key Features

- **Code execution** - Run Python, JS, Shell, and more
- **System access** - Interact with files, browsers, terminals
- **Conversational** - Natural language commands
- **Vision support** - Analyze images and screenshots
- **Computer control** - Mouse, keyboard, screen interaction
- **Safety controls** - Confirmation before execution

#### Best For

- Developers wanting a coding assistant
- System automation tasks
- Quick scripting and prototyping
- Interactive code exploration

#### Installation

```bash
pip install open-interpreter
```

#### Example: Using with Local Model

```bash
# Run with Ollama
interpreter --model ollama/llama3.1:8b

# Or in Python
```

```python
from interpreter import interpreter

interpreter.llm.model = "ollama/llama3.1:8b"
interpreter.llm.api_base = "http://localhost:11434"

interpreter.chat("Create a bar chart of the top 5 programming languages")
```

#### Limitations

- Security risk if not careful
- Quality depends heavily on model capability
- Code execution can be slow

---

### OpenHands

**Software Development Agent**

- **GitHub**: [OpenHands/OpenHands](https://github.com/OpenHands/OpenHands)
- **Stars**: 45,000+
- **Language**: Python
- **License**: MIT

#### Overview

OpenHands (formerly OpenDevin) is a platform for AI-powered software development agents. It provides a sandboxed environment where agents can write code, run commands, and browse the web.

#### Key Features

- **Docker sandbox** - Secure, isolated execution
- **Code editing** - Full file system access
- **Web browsing** - Research capabilities
- **Git integration** - Version control support
- **Multi-model** - Works with various LLMs
- **Agent modes** - Different agent strategies

#### Best For

- Software development tasks
- Code generation and modification
- Projects requiring isolated execution
- Teams wanting DevOps automation

#### Installation

```bash
# Requires Docker
docker pull ghcr.io/all-hands-ai/openhands:latest

# Run
docker run -it --rm \
  -e LLM_MODEL=ollama/llama3.1:8b \
  -e LLM_BASE_URL=http://host.docker.internal:11434 \
  -p 3000:3000 \
  ghcr.io/all-hands-ai/openhands:latest
```

#### Limitations

- Docker dependency
- Resource-intensive
- Complex setup for some configurations

---

### Dify

**Visual AI Application Builder**

- **GitHub**: [langgenius/dify](https://github.com/langgenius/dify)
- **Stars**: 55,000+
- **Language**: Python, TypeScript
- **License**: Apache-2.0

#### Overview

Dify is an open-source platform for building AI applications with a visual workflow editor. It combines the best of no-code and code-based approaches.

#### Key Features

- **Visual workflow builder** - Drag-and-drop interface
- **RAG pipeline** - Built-in retrieval augmented generation
- **Prompt IDE** - Visual prompt engineering
- **Agent capabilities** - Tool-using agents
- **Dataset management** - Organize knowledge bases
- **Observability** - Logging and monitoring

#### Best For

- Teams preferring visual development
- Rapid prototyping
- RAG applications
- Non-developers building AI apps

#### Installation

```bash
# Docker deployment
git clone https://github.com/langgenius/dify.git
cd dify/docker
docker compose up -d
```

#### Configuration for Local LLM

In the Dify UI, add Ollama as a model provider:
- Provider: Ollama
- Base URL: http://host.docker.internal:11434
- Model: llama3.1:8b

#### Limitations

- Heavier resource requirements
- Less flexible than pure code approaches
- Learning curve for the platform

---

### Flowise

**Drag-and-Drop LLM Flows**

- **GitHub**: [FlowiseAI/Flowise](https://github.com/FlowiseAI/Flowise)
- **Stars**: 32,000+
- **Language**: TypeScript
- **License**: Apache-2.0

#### Overview

Flowise is a visual tool for building LLM applications using a node-based editor. It's built on LangChain but provides a user-friendly interface.

#### Key Features

- **Visual editor** - Node-based flow creation
- **LangChain integration** - Uses LangChain under the hood
- **API generation** - Auto-generates APIs for flows
- **Template marketplace** - Pre-built flows
- **Custom nodes** - Extend with JavaScript
- **Multi-modal** - Support for images and documents

#### Best For

- Users preferring visual development
- Quick API creation
- LangChain users wanting a GUI
- Prototyping before coding

#### Installation

```bash
npm install -g flowise
npx flowise start
```

#### Limitations

- Less flexible than code
- Performance overhead from GUI
- Limited for very complex flows

---

## Tier 3: Emerging

These frameworks are newer but show significant promise.

### SmolAgents

**Minimal, Efficient Agents**

- **GitHub**: [huggingface/smolagents](https://github.com/huggingface/smolagents)
- **Stars**: 15,000+
- **Language**: Python
- **License**: Apache-2.0

#### Overview

SmolAgents from Hugging Face is a minimal agent framework in approximately 1,000 lines of code. It focuses on simplicity and efficiency while supporting code execution.

#### Key Features

- **Minimal codebase** - ~1000 lines of code
- **Code execution** - Agents write and run code
- **Tool integration** - Easy custom tools
- **Multi-model** - Works with various LLMs
- **Hugging Face integration** - Native HF ecosystem support
- **Lightweight** - Low overhead

#### Best For

- Users wanting simplicity
- Learning agent internals
- Lightweight deployments
- Hugging Face ecosystem users

#### Installation

```bash
pip install smolagents
```

#### Example

```python
from smolagents import CodeAgent, OllamaModel

model = OllamaModel(model_id="llama3.1:8b")

agent = CodeAgent(
    tools=[],  # Add custom tools
    model=model
)

result = agent.run("Calculate the first 10 fibonacci numbers")
```

#### Limitations

- Fewer features than larger frameworks
- Limited documentation
- Smaller community

---

### Agno

**Multimodal Agent Teams**

- **GitHub**: [agno-agi/agno](https://github.com/agno-agi/agno)
- **Stars**: 20,000+
- **Language**: Python
- **License**: MIT

#### Overview

Agno enables building teams of multimodal AI agents. It supports text, images, audio, and video processing with a focus on collaboration.

#### Key Features

- **Multimodal** - Text, image, audio, video
- **Team coordination** - Multiple agents working together
- **Streaming** - Real-time responses
- **Structured output** - Typed responses
- **Memory** - Persistent agent memory
- **Reasoning** - Built-in reasoning capabilities

#### Best For

- Multimodal applications
- Complex agent teams
- Applications requiring various media types
- Advanced reasoning tasks

#### Installation

```bash
pip install agno
```

#### Limitations

- Newer, less battle-tested
- Multimodal requires capable models
- Growing documentation

---

### Pydantic AI

**Type-Safe Agent Framework**

- **GitHub**: [pydantic/pydantic-ai](https://github.com/pydantic/pydantic-ai)
- **Stars**: 10,000+
- **Language**: Python
- **License**: MIT

#### Overview

Pydantic AI brings type safety and validation to AI agents. It leverages Pydantic's data validation to ensure structured, reliable outputs.

#### Key Features

- **Type validation** - Structured outputs guaranteed
- **Dependencies injection** - Clean architecture
- **Streaming** - Token and structured streaming
- **Testing support** - Built-in testing utilities
- **Logfire integration** - Observability
- **Model agnostic** - Works with many LLMs

#### Best For

- Applications requiring reliable outputs
- Teams valuing type safety
- Production systems needing validation
- Python developers familiar with Pydantic

#### Installation

```bash
pip install pydantic-ai
```

#### Example

```python
from pydantic_ai import Agent
from pydantic import BaseModel

class CityInfo(BaseModel):
    name: str
    country: str
    population: int
    interesting_fact: str

agent = Agent(
    'ollama:llama3.1:8b',
    result_type=CityInfo,
    system_prompt="You are a helpful geography assistant."
)

result = agent.run_sync("Tell me about Paris")
print(result.data)  # Validated CityInfo object
```

#### Limitations

- Focused primarily on structured outputs
- Less emphasis on multi-agent
- Requires understanding of Pydantic

---

### Goose

**Block's Extensible Agent**

- **GitHub**: [aaif-goose/goose](https://github.com/aaif-goose/goose)
- **Stars**: 8,000+
- **Language**: Python
- **License**: Apache-2.0

#### Overview

Goose is Block's (formerly Square) framework for building AI agents. It emphasizes extensibility and practical developer workflows.

#### Key Features

- **Toolkit system** - Extensible capabilities
- **Session management** - Persistent conversations
- **Shell integration** - Terminal-based interface
- **Provider support** - Multiple LLM providers
- **Exchange format** - Structured message format
- **Developer focus** - Built for dev workflows

#### Best For

- Developer tooling
- Terminal-based workflows
- Teams wanting extensibility
- Block ecosystem users

#### Installation

```bash
pip install goose-ai
```

#### Limitations

- Smaller community
- Less documentation
- More focused scope

---

### Letta

**Persistent Memory Agents**

- **GitHub**: [letta-ai/letta](https://github.com/letta-ai/letta)
- **Stars**: 12,000+
- **Language**: Python
- **License**: Apache-2.0

#### Overview

Letta (formerly MemGPT) focuses on persistent memory for AI agents. It uses vector databases to give agents true long-term memory.

#### Key Features

- **Persistent memory** - True long-term recall
- **Memory management** - Automatic memory organization
- **Vector databases** - Multiple DB support
- **Stateful agents** - Agents remember across sessions
- **Multi-agent** - Coordinated agent systems
- **API server** - Deploy as a service

#### Best For

- Applications requiring memory
- Long-running agent sessions
- Personal assistants
- Agents that learn over time

#### Installation

```bash
pip install letta
```

#### Limitations

- More complex architecture
- Requires database setup
- Memory management overhead

---

### Cline / Roo

**VS Code Agent Integration**

- **Marketplace**: VS Code Extension
- **Language**: TypeScript
- **License**: Apache-2.0

#### Overview

Cline (and its fork Roo) are VS Code extensions that bring AI agents directly into your editor. They can edit files, run commands, and assist with development.

#### Key Features

- **VS Code integration** - Native editor experience
- **File editing** - Direct code modification
- **Terminal access** - Run commands
- **Git integration** - Version control support
- **Local model support** - Works with Ollama
- **Context awareness** - Understands project structure

#### Best For

- VS Code users
- Interactive development
- Code modification tasks
- IDE-integrated workflows

#### Installation

1. Open VS Code Extensions
2. Search for "Cline" or "Roo"
3. Install and configure with Ollama

#### Limitations

- VS Code only
- Limited to extension capabilities
- UI constraints

---

## Framework Comparison Matrix

| Framework | Multi-Agent | RAG | Code Exec | Visual | Memory | Local LLM | Learning Curve |
|-----------|-------------|-----|-----------|--------|--------|-----------|----------------|
| LangChain | Via tools | ✅ | ✅ | ❌ | ✅ | ✅ | High |
| LangGraph | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | High |
| CrewAI | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | Low |
| AutoGen | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | Medium |
| AutoGPT | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | Medium |
| Open Interpreter | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | Low |
| OpenHands | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | Medium |
| Dify | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | Low |
| Flowise | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ | Low |
| SmolAgents | ❌ | ❌ | ✅ | ❌ | ❌ | ✅ | Low |
| Agno | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | Medium |
| Pydantic AI | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | Low |
| Goose | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | Low |
| Letta | ✅ | ✅ | ❌ | ❌ | ✅ | ✅ | Medium |

---

## Choosing the Right Framework

### By Use Case

**Building Complex Enterprise Applications**
- First choice: LangChain + LangGraph
- Alternative: AutoGen

**Rapid Prototyping Multi-Agent Systems**
- First choice: CrewAI
- Alternative: AutoGen

**Code Generation and Development**
- First choice: Open Interpreter
- Alternative: OpenHands

**Visual/No-Code Development**
- First choice: Dify
- Alternative: Flowise

**Learning Agent Internals**
- First choice: SmolAgents
- Alternative: Pydantic AI

**Persistent Memory Applications**
- First choice: Letta
- Alternative: LangChain with custom memory

### By Team Experience

**Beginners**
1. CrewAI - Simplest multi-agent
2. Open Interpreter - Easy code execution
3. Flowise - Visual building

**Intermediate**
1. LangChain - Flexible and powerful
2. AutoGen - Microsoft's approach
3. Dify - Full-featured visual

**Advanced**
1. LangGraph - Complex state management
2. Custom LangChain - Full control
3. SmolAgents - Build from scratch

### By Resource Constraints

**Limited Compute**
1. SmolAgents - Minimal overhead
2. Open Interpreter - Single agent
3. Pydantic AI - Lightweight

**Full Resources Available**
1. LangGraph - Complex orchestration
2. OpenHands - Docker sandboxing
3. Dify - Full platform

---

## Historical November 2025 Framework Notes

These notes retain the November 2025 release context. They are not a current ranking; use the shortlist above for current choices.

### Composio

**100+ High-Quality Integrations**

- **GitHub**: [ComposioHQ/composio](https://github.com/ComposioHQ/composio)
- **Stars**: 26.2K+
- **Language**: Python
- **License**: Apache-2.0

#### Overview

Composio provides 100+ high-quality integrations via function calling, supporting MCP and SSE for seamless tool integration with any LLM or agent framework.

#### Key Features

- **100+ integrations** - Extensive tool library
- **Function calling** - Native LLM support
- **MCP support** - Model Context Protocol compatible
- **SSE streaming** - Server-Sent Events for real-time
- **Framework agnostic** - Works with any agent framework

---

### EvoAgentX

**Self-Evolving AI Agent Ecosystem**

- **GitHub**: [EvoAgentX/EvoAgentX](https://github.com/EvoAgentX/EvoAgentX)
- **Language**: Python
- **License**: MIT

#### Overview

EvoAgentX is a self-evolving ecosystem of AI agents featuring TextGrad, MIPRO, and AFlow algorithms for continuous improvement and optimization.

#### Key Features

- **Self-evolution** - Agents improve over time
- **TextGrad** - Text-based gradient optimization
- **MIPRO** - Multi-objective optimization
- **AFlow** - Adaptive workflow patterns
- **Ecosystem approach** - Holistic agent development

---

### Parlant

**LLM Agents Built for Control**

- **GitHub**: [parlant/parlant](https://github.com/parlant/parlant)
- **Stars**: 16.3K+
- **Language**: Python
- **License**: Apache-2.0

#### Overview

Parlant focuses on building LLM agents with fine-grained control, allowing deployment in minutes while maintaining full observability.

#### Key Features

- **Control-first design** - Fine-grained agent control
- **Quick deployment** - Minutes to production
- **Full observability** - Comprehensive monitoring
- **Safety features** - Built-in guardrails
- **Production ready** - Enterprise-grade reliability

---

### Agno (v2.0)

**Multi-Agent Runtime and Control Plane**

- **GitHub**: [agno-agi/agno](https://github.com/agno-agi/agno)
- **Stars**: 35.4K+
- **Language**: Python
- **License**: MIT

#### Overview

Agno v2.0 is a multi-agent framework with dedicated runtime and control plane, built for speed, privacy, and scale in enterprise deployments.

#### Key Features

- **Control plane** - Centralized agent management
- **Runtime engine** - Optimized execution environment
- **Privacy-first** - Local-first architecture
- **Horizontal scaling** - Enterprise scalability
- **Multimodal** - Text, image, audio, video

---

### Daytona

**Secure and Elastic AI Code Infrastructure**

- **GitHub**: [daytonaio/daytona](https://github.com/daytonaio/daytona)
- **Stars**: 32.3K+
- **Language**: Go
- **License**: Apache-2.0

#### Overview

Daytona provides secure and elastic infrastructure specifically designed for running AI-generated code safely at scale.

#### Key Features

- **Secure sandbox** - Isolated code execution
- **Elastic scaling** - Auto-scales with demand
- **AI-optimized** - Built for generated code
- **DevContainer support** - Standard container specs
- **Multi-cloud** - Any infrastructure provider

---

### MS-Agent v1.5.0

**Lightweight Multi-Agent Framework**

- **GitHub**: [microsoft/ms-agent](https://github.com/microsoft/ms-agent)
- **Language**: Python
- **License**: MIT

#### Overview

MS-Agent v1.5.0 is a lightweight framework featuring FinResearch multi-agent workflow for financial analysis and research automation.

#### Key Features

- **FinResearch workflow** - Financial analysis agents
- **Lightweight** - Minimal resource usage
- **Multi-agent** - Coordinated agent systems
- **Domain-specific** - Finance-optimized patterns
- **Microsoft backing** - Enterprise support

---

### Swarms Framework

**Bleeding-Edge Multi-Agent Orchestration**

- **GitHub**: [swarms/swarms](https://github.com/kyegomez/swarms)
- **Language**: Python
- **License**: MIT

#### Overview

Swarms is a bleeding-edge multi-agent orchestration framework designed for enterprise-scale deployments with advanced coordination patterns.

#### Key Features

- **Enterprise scale** - Handles thousands of agents
- **Advanced patterns** - Sophisticated orchestration
- **Production ready** - Battle-tested in enterprise
- **Extensible** - Plugin architecture
- **High performance** - Optimized for throughput

---

### AgentUp

**Security-First Agent Framework**

- **GitHub**: [agentup/agentup](https://github.com/agentup/agentup)
- **Language**: Python
- **License**: Apache-2.0

#### Overview

AgentUp prioritizes security, scalability, and extensibility as first-class features for building trustworthy agent systems.

#### Key Features

- **Security-first** - Built-in security patterns
- **Scalable** - Horizontal and vertical scaling
- **Extensible** - Clean plugin system
- **Auditable** - Comprehensive logging
- **Compliant** - Enterprise compliance support

---

### Upsonic

**Reliable Agent Framework with MCP**

- **GitHub**: [upsonic/upsonic](https://github.com/upsonic/upsonic)
- **Language**: Python
- **License**: MIT

#### Overview

Upsonic is a reliable agent framework with MCP support and verification layers for ensuring agent output quality and safety.

#### Key Features

- **MCP support** - Model Context Protocol native
- **Verification layers** - Output validation
- **Reliability focus** - Error handling and recovery
- **Tool integration** - Extensive tool support
- **Production grade** - Ready for deployment

---

### Mastra

**Opinionated TypeScript Agent Framework**

- **GitHub**: [mastra/mastra](https://github.com/mastra/mastra)
- **Language**: TypeScript
- **License**: MIT

#### Overview

Mastra is an opinionated TypeScript framework for building AI applications with strong typing and modern JavaScript patterns.

#### Key Features

- **TypeScript native** - Full type safety
- **Opinionated** - Best practices baked in
- **Modern stack** - Latest JS/TS features
- **React integration** - Frontend-friendly
- **DX focused** - Great developer experience

---

### LLMling-Agent

**YAML-Driven Multi-Agent Workflows**

- **GitHub**: [llmling/llmling-agent](https://github.com/llmling/llmling-agent)
- **Language**: Python
- **License**: MIT

#### Overview

LLMling-Agent enables multi-agent workflows defined via YAML manifest files, making agent orchestration declarative and version-controllable.

#### Key Features

- **YAML configuration** - Declarative agent definition
- **Version control** - Git-friendly workflows
- **Multi-agent** - Coordinated systems
- **Reproducible** - Consistent deployments
- **Low-code** - Minimal coding required

---

### FastGPT

**AI Agent Building Platform**

- **GitHub**: [labring/FastGPT](https://github.com/labring/FastGPT)
- **Stars**: 25.5K+
- **Language**: TypeScript
- **License**: Apache-2.0

#### Overview

FastGPT is an AI agent building platform with visual workflows and knowledge base integration for rapid agent development.

#### Key Features

- **Visual workflows** - Drag-and-drop builder
- **Knowledge base** - Built-in RAG
- **Multi-modal** - Various input types
- **API generation** - Auto-generated endpoints
- **Self-hosted** - Full control over data

---

### Agent Lightning (Microsoft)

**AI Agent Trainer Framework**

- **GitHub**: [microsoft/agent-lightning](https://github.com/microsoft/agent-lightning)
- **Language**: Python
- **License**: MIT

#### Overview

Agent Lightning from Microsoft is a trainer framework for AI agents, enabling rapid skill development and capability enhancement.

#### Key Features

- **Training focused** - Agent skill development
- **Fast iteration** - Quick training cycles
- **Evaluation tools** - Agent benchmarking
- **Microsoft backed** - Enterprise support
- **Research-grade** - Latest techniques

---

### Giselle

**Agentic Workflow Builder**

- **GitHub**: [giselle/giselle](https://github.com/giselle/giselle)
- **Language**: TypeScript
- **License**: MIT

#### Overview

Giselle is an agentic workflow builder for creating sophisticated AI workflows with visual design and code generation.

#### Key Features

- **Visual builder** - Intuitive design interface
- **Code generation** - Export to code
- **Workflow templates** - Pre-built patterns
- **Real-time preview** - Live workflow testing
- **Team collaboration** - Shared workspaces

---

### Pinokio

**Browser for AI Applications**

- **GitHub**: [pinokio/pinokio](https://github.com/pinokio/pinokio)
- **Language**: JavaScript
- **License**: MIT

#### Overview

Pinokio is a browser that installs, runs, and automates AI applications locally with one-click setup for complex AI tools.

#### Key Features

- **One-click install** - Easy AI app setup
- **Browser interface** - Familiar UX
- **Automation** - Script AI workflows
- **Cross-platform** - Windows, Mac, Linux
- **App ecosystem** - Growing library

---

### Kimi CLI

**Open-Source CLI Agent from Moonshot AI**

- **GitHub**: [moonshot/kimi-cli](https://github.com/moonshot/kimi-cli)
- **Language**: Python
- **License**: Apache-2.0

#### Overview

Kimi CLI is an open-source command-line agent from Moonshot AI featuring 128K context window and MCP support for complex tasks.

#### Key Features

- **128K context** - Massive context window
- **MCP support** - Model Context Protocol
- **CLI-first** - Terminal-native experience
- **Tool calling** - Extensive tool support
- **Open source** - Full transparency

---

## Conclusion

The local AI agent ecosystem offers diverse options for different needs:

- **LangChain/LangGraph** - Maximum flexibility and control
- **CrewAI** - Simplest path to multi-agent systems
- **AutoGen** - Research-backed conversational agents
- **Open Interpreter** - Direct code execution
- **Dify/Flowise** - Visual development
- **Composio** - Tool integrations; verify the current connector surface upstream
- **Agno** - Model-agnostic agents with tools, knowledge, and memory
- **Daytona** - Secure AI code execution and developer environments

Start with your use case and team experience level, then iterate as your needs grow. All these frameworks support local LLMs through Ollama or similar tools, giving you complete control over your AI agent stack.

---

Last Updated: 2 August 2026; historical examples remain version-sensitive.
