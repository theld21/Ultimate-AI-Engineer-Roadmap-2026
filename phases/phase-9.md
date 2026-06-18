## 🗺️ PHASE 9 - AI Agents & Agentic Systems

> **Goal:** Build autonomous AI systems that can reason, plan, and take actions.

### 9.1 What Are AI Agents

- Agent = LLM + Tools + Memory + Planning
- Difference between chain and agent - agents decide dynamically
- Types: ReAct, Plan-and-Execute, Multi-agent
- When to use agents vs chains
- Risks: cost, hallucination, infinite loops

### 9.2 Agent Components

**Tools / Functions**
- Web search tools (Tavily, SerpAPI, Bing)
- Code interpreter / execution
- Calculator
- Database query tool
- File read/write tool
- API call tools
- Web scraping tools
- Calendar, email, calendar tools (via MCP)

**Memory Systems**
- In-context memory - conversation history in prompt
- External memory - vector store of past interactions
- Entity memory - tracking mentioned entities
- Summary memory - compress old conversation
- Episodic memory - remember specific past events

**Planning Strategies**
- ReAct (Reason + Act) - interleave thinking and action
- Plan-and-execute - generate full plan first, then execute
- Tree of Thoughts - explore multiple reasoning paths
- MRKL (Modular Reasoning, Knowledge, Language)

### 9.3 Function Calling / Tool Use

**OpenAI Tool Use**
- Define tools as JSON schemas
- Attach to API call
- Parse tool call responses
- Execute tool, return result
- Continue conversation with tool result
- Parallel tool calls

**Anthropic Tool Use**
- Tool definition format
- Tool result format
- Multi-tool usage

**Building Robust Tool Systems**
- Tool validation - input schema validation
- Tool error handling - graceful failure
- Tool timeouts
- Tool authorization - what can the agent do?
- Sandboxed code execution

### 9.4 Multi-Agent Systems

**Patterns**
- Supervisor → Worker agents (hierarchical)
- Peer-to-peer agents (collaborative)
- Pipeline agents (sequential specialists)
- Adversarial agents (critic + generator)

**LangGraph for Multi-Agent**
- Stateful graphs with shared state
- Conditional edges - dynamic routing
- Parallel execution of agents
- Human-in-the-loop checkpoints
- Agent communication protocols

**Real-World Multi-Agent Use Cases**
- Code review system: Writer + Reviewer + Tester agents
- Research system: Planner + Researcher + Synthesizer agents
- Software development: PM + Engineer + QA agents (Devin-style)
- Customer support: Classifier + Specialist + Escalation agents

### 9.5 Agentic AI (AskAI Framework)

**Agentic Principles**
- Autonomy - agents make decisions without human input per step
- Goal-directedness - agents work toward specified objectives
- Persistence - agents maintain state across interactions
- Adaptability - agents adjust based on feedback

**Production Agentic Systems**
- Task decomposition - breaking complex tasks into subtasks
- Progress tracking - monitoring multi-step completion
- Error recovery - retrying failed steps
- Human escalation - when to pause and ask for input
- Audit trails - logging every agent decision

**Safety in Agents**
- Action confirmation for irreversible operations
- Scope limitation - what agents can and cannot do
- Cost controls - maximum spend per agent run
- Sandboxing code execution
- Input/output validation

---

### 📦 Phase 9 Projects

**🟢 Easy: ReAct Agent with Web Search**
- Build an agent that can search the web to answer current events questions
- Tools: Tavily search, calculator, current date
- Stack: LangChain, OpenAI, Tavily API

**🟡 Medium: Code Review Agent**
- Multi-agent: Reviewer (finds issues), Improver (suggests fixes), Tester (writes tests)
- Supports Python and JavaScript
- Stack: LangGraph, OpenAI, Docker (sandboxed execution)

**🔴 Hard: Autonomous Research Agent (AskAI)**
- Given a research question, agent: decomposes into sub-questions, searches web + internal knowledge base, reads papers, synthesizes findings, writes a structured report
- Features: parallel research, source citation, confidence scoring, human approval checkpoints
- Stack: LangGraph, OpenAI + Claude, Tavily, Pinecone, FastAPI, React, Redis for state

---

