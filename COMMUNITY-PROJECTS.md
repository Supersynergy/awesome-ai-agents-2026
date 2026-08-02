# Community Projects - Real-World Local Agent Implementations

> **Freshness boundary (2 August 2026):** The live shortlist below was checked against official GitHub metadata. The tutorial and implementation sections remain intentionally long-form examples; they are not a current activity ranking. Use the [current README](README.md) and [update audit](docs/UPDATE-2026-08-02.md) for current entries.

A collection of community-built local AI agent projects, tutorials, and production deployments for inspiration and learning.

## Table of Contents

- [Current Shortlist (2 August 2026)](#current-shortlist-2-august-2026)
- [Historical project examples](#historical-project-examples)
- [Community-Built Agents](#community-built-agents)
- [Open-Source Implementations](#open-source-implementations)
- [Tutorial Projects](#tutorial-projects)
- [Production Deployments](#production-deployments)
- [Project Templates](#project-templates)
- [Contributing Your Project](#contributing-your-project)

---

## Current Shortlist (2 August 2026)

Stars are GitHub snapshots from the update pass, not quality scores. These projects were selected because they have a concrete agent job, an active upstream repository, and a current signal from ghmax or the comparison-list pass.

### Developer tools and coding-agent operations

| Project | Stars | Description | Stack |
|---------|-------|-------------|-------|
| [OpenCode](https://github.com/anomalyco/opencode) | 192.0K | Open-source, model-agnostic coding agent | TypeScript |
| [OpenHands](https://github.com/OpenHands/OpenHands) | 82.8K | Autonomous software-development workflows | Python |
| [Open Interpreter](https://github.com/openinterpreter/openinterpreter) | 67.5K | Code-capable agent for open models | Rust |
| [CodeGraph](https://github.com/colbymchenry/codegraph) | 63.9K | Local code knowledge graph for coding agents | C |
| [Qwen Code](https://github.com/QwenLM/qwen-code) | 26.5K | Open-source terminal coding agent | TypeScript |
| [Beads](https://github.com/gastownhall/beads) | 25.8K | Persistent work and memory layer for coding agents | Go |
| [AgenticFlowX](https://github.com/AgenticFlowX/agenticflowx) | 19 | VS Code AI coding workflow with Code, Explore, Spec, skills, and traceability | TypeScript |
| [OpenTag](https://github.com/CopilotKit/OpenTag) | 723 | Agent-native on-call triage assistant for Slack and Microsoft Teams | TypeScript / Python |

### Runtimes, workspaces, and orchestration

| Project | Stars | Description | Stack |
|---------|-------|-------------|-------|
| [OpenClaw](https://github.com/openclaw/openclaw) | 384.8K | Self-hosted personal assistant with channels and skills | TypeScript |
| [Hermes Agent](https://github.com/NousResearch/hermes-agent) | 223.8K | Long-lived local agent with skills and learning | Python |
| [nanobot](https://github.com/HKUDS/nanobot) | 46.5K | Lightweight self-hosted agent with tools, memory, MCP, and chat apps | Python |
| [ZeroClaw](https://github.com/zeroclaw-labs/zeroclaw) | 32.5K | Small Rust personal-assistant infrastructure | Rust |
| [herdr](https://github.com/herdrdev/herdr) | 23.4K | Runtime and workspace manager for coding-agent fleets | Rust |
| [Kun](https://github.com/KunAgent/Kun) | 5.5K | Local-first GUI/TUI workspace for coding, writing, and research | TypeScript |
| [Mission Control](https://github.com/builderz-labs/mission-control) | 5.9K | Self-hosted dispatch, review, operations, and spend tracking | TypeScript |
| [AgenticROS](https://github.com/agenticros/agenticros) | 128 | ROS 2 bridge for OpenClaw, Claude, Codex, Gemini, Hermes, and MCP | TypeScript |
| [Autonomous OS](https://github.com/autonomous-ai/autonomous-os) | 23 | Local-first operating system for physical AI agents and devices | Go / Python |
| [Wippy](https://github.com/wippyai/runtime) | 12 | Durable actor runtime with queues, vector search, policy controls, and MCP updates | Go / Lua / WASM |

### Sandboxing, context, and security

| Project | Stars | Description | Stack |
|---------|-------|-------------|-------|
| [OpenSandbox](https://github.com/opensandbox-group/OpenSandbox) | 12.3K | Secure sandbox runtime with agent, browser, and Kubernetes examples | Python |
| [NVIDIA OpenShell](https://github.com/NVIDIA/OpenShell) | 7.9K | Policy-governed private runtime for agents; alpha software | Rust |
| [OpenViking](https://github.com/volcengine/OpenViking) | 27.7K | Filesystem-shaped context database for memory, RAG, and skills | Python |
| [Snyk Agent Scan](https://github.com/snyk/agent-scan) | 2.8K | Scans agent components, MCP servers, and skills for threats | Python |
| [Blaxel Sandbox](https://github.com/blaxel-ai/sandbox) | 25 | Isolated micro-VM templates and sandbox API for agent workloads | Go |

---

## Historical project examples

### Developer Tools

| Project | Stars | Description | Stack |
|---------|-------|-------------|-------|
| [aider](https://github.com/Aider-AI/aider) | 47.9K | AI pair programming in terminal | Python |
| [gpt-engineer](https://github.com/gpt-engineer-org/gpt-engineer) | 51K+ | AI code generation from specs | Python |
| [devika](https://github.com/stitionai/devika) | 18K+ | Agentic AI software engineer | Python, LangChain |
| [continue](https://github.com/continuedev/continue) | 25K+ | Open-source AI code assistant | TypeScript |
| [cursor](https://cursor.so) | Popular | AI-first code editor | Proprietary |
| [tabby](https://github.com/TabbyML/tabby) | 20K+ | Self-hosted AI coding assistant | Rust |

### Research and Analysis

| Project | Stars | Description | Stack |
|---------|-------|-------------|-------|
| [gpt-researcher](https://github.com/assafelovic/gpt-researcher) | 16K+ | Autonomous research agent | Python, LangChain |
| [khoj](https://github.com/khoj-ai/khoj) | 15K+ | Personal AI for search/chat | Python |
| [anything-llm](https://github.com/Mintplex-Labs/anything-llm) | 28K+ | All-in-one desktop AI | JavaScript |
| [quivr](https://github.com/QuivrHQ/quivr) | 38K+ | Personal AI second brain | Python, FastAPI |
| [danswer](https://github.com/danswer-ai/danswer) | 12K+ | Enterprise QA system | Python |

### Automation and Workflows

| Project | Stars | Description | Stack |
|---------|-------|-------------|-------|
| [autogen-studio](https://github.com/microsoft/autogen) | Part of AutoGen | Visual multi-agent builder | Python |
| [langflow](https://github.com/logspace-ai/langflow) | 35K+ | Visual agent builder | Python, React |
| [n8n](https://github.com/n8n-io/n8n) | 50K+ | Workflow automation with AI | TypeScript |
| [activepieces](https://github.com/activepieces/activepieces) | 10K+ | No-code automation | TypeScript |

### Personal Assistants

| Project | Stars | Description | Stack |
|---------|-------|-------------|-------|
| [open-webui](https://github.com/open-webui/open-webui) | 60K+ | Self-hosted ChatGPT UI | Python, Svelte |
| [librechat](https://github.com/danny-avila/LibreChat) | 18K+ | Enhanced ChatGPT clone | JavaScript |
| [lobe-chat](https://github.com/lobehub/lobe-chat) | 50K+ | Modern chat UI | TypeScript |
| [big-agi](https://github.com/enricoros/big-AGI) | 5K+ | Personal AI suite | TypeScript |

---

## Community-Built Agents

### Coding Agents

#### LocalCodeReviewer
A local code review agent that analyzes PRs without sending code to external services.

```python
# Example implementation
from crewai import Agent, Task, Crew
from langchain_ollama import OllamaLLM

llm = OllamaLLM(model="deepseek-coder-v2:16b")

code_reviewer = Agent(
    role="Senior Code Reviewer",
    goal="Review code for bugs, security issues, and best practices",
    backstory="20 years of software engineering experience",
    llm=llm
)

security_auditor = Agent(
    role="Security Auditor",
    goal="Identify security vulnerabilities and compliance issues",
    backstory="Certified security professional",
    llm=llm
)

review_task = Task(
    description="Review the provided code diff for issues",
    expected_output="Detailed review with line-by-line comments",
    agent=code_reviewer
)

crew = Crew(
    agents=[code_reviewer, security_auditor],
    tasks=[review_task]
)
```

**Use Cases:**
- Pre-commit code review
- Security scanning
- Style enforcement
- Documentation validation

---

#### TestGenerator
Automatically generate unit tests for existing code.

```python
from langchain_ollama import OllamaLLM
from langchain.agents import create_react_agent

llm = OllamaLLM(model="qwen2.5-coder:14b")

test_generator_prompt = """
Analyze the provided code and generate comprehensive unit tests.
Include edge cases, error handling, and documentation.

Code to test:
{code}

Generate tests in {framework} format.
"""

# Use with LangChain agent for file reading and writing
```

---

### Research Agents

#### LocalResearcher
Multi-agent research system that works entirely offline.

```python
from crewai import Agent, Task, Crew, Process

# Agents for different research phases
gatherer = Agent(
    role="Information Gatherer",
    goal="Collect and organize information from local knowledge base",
    backstory="Expert at finding relevant information",
    llm=OllamaLLM(model="llama3.1:8b")
)

analyst = Agent(
    role="Research Analyst",
    goal="Analyze information and identify patterns",
    backstory="PhD researcher with analytical expertise",
    llm=OllamaLLM(model="qwen2.5:14b")
)

writer = Agent(
    role="Report Writer",
    goal="Synthesize findings into clear reports",
    backstory="Technical writer with research background",
    llm=OllamaLLM(model="llama3.1:8b")
)

# Sequential research workflow
crew = Crew(
    agents=[gatherer, analyst, writer],
    tasks=[gather_task, analyze_task, write_task],
    process=Process.sequential
)
```

---

### Automation Agents

#### PersonalEmailAssistant
Local email processing agent that never sends data externally.

```python
from langchain_ollama import OllamaLLM
from langchain.agents import initialize_agent

llm = OllamaLLM(model="llama3.1:8b")

tools = [
    EmailReader(),      # Read emails from local IMAP
    EmailCategorizer(), # Classify emails
    DraftWriter(),      # Generate draft responses
    CalendarChecker(),  # Check availability
]

assistant = initialize_agent(
    tools=tools,
    llm=llm,
    agent="zero-shot-react-description",
    verbose=True
)

# Process incoming emails
result = assistant.run("Process new emails and draft responses")
```

---

## Open-Source Implementations

### Full Applications

#### Private GPT
Run completely private ChatGPT with your documents.

**Repository:** [privateGPT](https://github.com/zylon-ai/private-gpt)

**Features:**
- 100% local execution
- Document ingestion
- RAG implementation
- Multiple LLM support

**Setup:**
```bash
git clone https://github.com/zylon-ai/private-gpt
cd private-gpt
poetry install
python -m private_gpt
```

---

#### LocalGPT
Chat with your documents locally.

**Repository:** [LocalGPT](https://github.com/PromtEngineer/localGPT)

**Features:**
- Document Q&A
- Multiple embedding options
- GPU acceleration
- Web UI included

---

### Agent Frameworks

#### BabyAGI
Task-driven autonomous agent.

**Repository:** [babyagi](https://github.com/yoheinakajima/babyagi)

**Concepts:**
- Task creation
- Task prioritization
- Task execution
- Memory management

**Adaptation for Local:**
```python
# Replace OpenAI with Ollama
from langchain_ollama import OllamaLLM

llm = OllamaLLM(model="llama3.1:8b")
embeddings = OllamaEmbeddings(model="nomic-embed-text")
```

---

## Tutorial Projects

### Beginner Projects

#### 1. Simple Chatbot with Memory
Learn basic agent concepts with conversation memory.

```python
from langchain_ollama import OllamaLLM
from langchain.memory import ConversationBufferMemory
from langchain.chains import ConversationChain

llm = OllamaLLM(model="llama3.1:8b")
memory = ConversationBufferMemory()

conversation = ConversationChain(
    llm=llm,
    memory=memory,
    verbose=True
)

# Chat
response = conversation.predict(input="Hello! I'm learning about AI agents.")
print(response)

response = conversation.predict(input="What did I just tell you?")
print(response)  # Should remember the previous message
```

**Learning Goals:**
- LLM initialization
- Memory systems
- Conversation chains

---

#### 2. Document Q&A Bot
Build a simple RAG application.

```python
from langchain_ollama import OllamaLLM, OllamaEmbeddings
from langchain.vectorstores import Chroma
from langchain.document_loaders import PyPDFLoader
from langchain.chains import RetrievalQA

# Load document
loader = PyPDFLoader("document.pdf")
documents = loader.load()

# Create embeddings and vector store
embeddings = OllamaEmbeddings(model="nomic-embed-text")
vectorstore = Chroma.from_documents(documents, embeddings)

# Create QA chain
llm = OllamaLLM(model="llama3.1:8b")
qa_chain = RetrievalQA.from_chain_type(
    llm=llm,
    chain_type="stuff",
    retriever=vectorstore.as_retriever()
)

# Ask questions
answer = qa_chain.invoke("What is the main topic of this document?")
print(answer)
```

**Learning Goals:**
- Document loading
- Vector embeddings
- Retrieval augmented generation

---

### Intermediate Projects

#### 3. Multi-Tool Agent
Create an agent that can use multiple tools.

```python
from langchain_ollama import OllamaLLM
from langchain.agents import Tool, create_react_agent, AgentExecutor
from langchain.prompts import PromptTemplate

llm = OllamaLLM(model="llama3.1:8b")

# Define tools
def calculator(expression: str) -> str:
    return str(eval(expression))

def file_reader(path: str) -> str:
    with open(path, 'r') as f:
        return f.read()

tools = [
    Tool(
        name="Calculator",
        func=calculator,
        description="Useful for math calculations"
    ),
    Tool(
        name="FileReader",
        func=file_reader,
        description="Read contents of a file"
    )
]

# Create agent
prompt = PromptTemplate.from_template("""...""")  # ReAct prompt
agent = create_react_agent(llm, tools, prompt)
executor = AgentExecutor(agent=agent, tools=tools, verbose=True)

result = executor.invoke({"input": "Calculate 15% of 200"})
```

**Learning Goals:**
- Tool creation
- ReAct pattern
- Agent execution

---

#### 4. Workflow Agent with LangGraph

```python
from langgraph.graph import StateGraph, END
from typing import TypedDict, List

class WorkflowState(TypedDict):
    task: str
    research: str
    analysis: str
    report: str

def research_node(state: WorkflowState) -> WorkflowState:
    llm = OllamaLLM(model="llama3.1:8b")
    state["research"] = llm.invoke(f"Research: {state['task']}")
    return state

def analysis_node(state: WorkflowState) -> WorkflowState:
    llm = OllamaLLM(model="llama3.1:8b")
    state["analysis"] = llm.invoke(f"Analyze: {state['research']}")
    return state

def report_node(state: WorkflowState) -> WorkflowState:
    llm = OllamaLLM(model="llama3.1:8b")
    state["report"] = llm.invoke(f"Report on: {state['analysis']}")
    return state

# Build graph
workflow = StateGraph(WorkflowState)
workflow.add_node("research", research_node)
workflow.add_node("analysis", analysis_node)
workflow.add_node("report", report_node)

workflow.set_entry_point("research")
workflow.add_edge("research", "analysis")
workflow.add_edge("analysis", "report")
workflow.add_edge("report", END)

app = workflow.compile()
```

**Learning Goals:**
- State management
- Graph-based workflows
- Node composition

---

### Advanced Projects

#### 5. Multi-Agent Software Team

```python
from crewai import Agent, Task, Crew, Process

# Full development team
architect = Agent(
    role="Software Architect",
    goal="Design system architecture",
    llm=OllamaLLM(model="qwen2.5:14b")
)

developer = Agent(
    role="Senior Developer",
    goal="Implement features with clean code",
    llm=OllamaLLM(model="deepseek-coder-v2:16b")
)

tester = Agent(
    role="QA Engineer",
    goal="Write comprehensive tests",
    llm=OllamaLLM(model="qwen2.5-coder:7b")
)

reviewer = Agent(
    role="Code Reviewer",
    goal="Review code quality and security",
    llm=OllamaLLM(model="llama3.1:8b")
)

# Tasks with dependencies
design_task = Task(
    description="Design architecture for {feature}",
    agent=architect
)

implement_task = Task(
    description="Implement based on architecture",
    agent=developer,
    context=[design_task]  # Depends on design
)

test_task = Task(
    description="Write tests for implementation",
    agent=tester,
    context=[implement_task]
)

review_task = Task(
    description="Review code and tests",
    agent=reviewer,
    context=[implement_task, test_task]
)

crew = Crew(
    agents=[architect, developer, tester, reviewer],
    tasks=[design_task, implement_task, test_task, review_task],
    process=Process.sequential
)
```

---

## Production Deployments

### Case Studies

#### Enterprise Document Processing
**Industry:** Legal
**Scale:** 10,000+ documents/day
**Stack:** LocalAI, LangChain, PostgreSQL

**Architecture:**
- Document ingestion pipeline
- Multi-model routing
- Vector search
- Audit logging

---

#### Customer Support Automation
**Industry:** E-commerce
**Scale:** 1,000+ tickets/day
**Stack:** Ollama, CrewAI, Redis

**Key Features:**
- Ticket classification
- Response generation
- Escalation rules
- Human review interface

---

#### Code Repository Analysis
**Industry:** Technology
**Scale:** 500+ repositories
**Stack:** Ollama, LangGraph, Neo4j

**Capabilities:**
- Dependency analysis
- Security scanning
- Documentation generation
- Refactoring suggestions

---

## Project Templates

### Starter Templates

- [LangChain + Ollama Template](https://github.com/example/langchain-ollama-starter)
- [CrewAI Local Starter](https://github.com/example/crewai-local-starter)
- [RAG Application Template](https://github.com/example/local-rag-template)
- [Multi-Agent Workflow](https://github.com/example/multi-agent-template)

### Boilerplates

- Full-stack agent application
- API-based agent service
- Desktop agent application
- CLI agent tool

---

## Contributing Your Project

Want to share your local AI agent project? We'd love to include it!

### Requirements

1. **Open source** - Project must be publicly available
2. **Local-first** - Must work with local LLMs
3. **Documented** - Include README and setup instructions
4. **Working** - Project should be functional

### How to Submit

1. Fork this repository
2. Add your project to the appropriate section
3. Include: name, description, link, stack
4. Submit a PR with details

### Template

```markdown
#### [Project Name](https://github.com/username/project)
Brief description of what it does.

**Stack:** Python, LangChain, Ollama
**Features:** Feature 1, Feature 2
**Status:** Active/Maintained
```

---

## Resources

- [r/LocalLLaMA](https://reddit.com/r/LocalLLaMA) - Community discussions
- [Hugging Face Spaces](https://huggingface.co/spaces) - Demo projects
- [GitHub Topics: AI Agents](https://github.com/topics/ai-agents)
- [LangChain Templates](https://github.com/langchain-ai/langchain/tree/master/templates)

---

Last Updated: 2 August 2026; historical examples are retained for tutorial continuity.
