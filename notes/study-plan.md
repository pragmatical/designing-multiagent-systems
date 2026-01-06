# 12-Week Multi-Agent Systems Study Plan

Using **Victor Dibia’s _Designing Multi-Agent Systems_** as the primary material.

This plan is designed for a study group meeting **once per week (60–90 minutes)**. Each week includes:

- **Reading** from the book
- **Learning goals**
- **Discussion prompts**
- **Hands-on exercises**
- **In-session group activities**

---

## Week 1 — Foundations I: Why Multi-Agent Systems?

**Reading**  

- Preface (skim)  
- Chapter 1: Sections 1.1–1.4 (Introduction; Why Multiple Agents; What is an Agent?)

**Goals**  

- Understand the progression: **model → agent → multi-agent system**.  
- Grasp the core agent capabilities: **reason, act, communicate, adapt**.  
- Recognize when tasks outgrow “single model” solutions.

**Key concepts**  

- Task complexity levels (Table 1.1)  
- Complex task characteristics: planning, diverse expertise, extensive context, adaptive solutions (Figure 1.4).citeturn4search1

**Discussion prompts**  

- Identify real tasks from your work that match each complexity level (model / agent / multi-agent).citeturn4search1  
- Where have you seen LLM-only solutions fail because of missing tools or planning?

**Hands-on exercise (individual)**  

- Implement a simple **prompt-only “agent”** (no tools) that answers Q&A and observe its limitations on tasks needing fresh data (e.g., “today’s stock price”).

**Group activity (session)**  

- Whiteboard the **reason–act–communicate–adapt loop** for a task your team cares about.citeturn4search1

---

## Week 2 — Foundations II: Agent and MAS Architecture

**Reading**  

- Chapter 1: Sections 1.4–1.9 (What is an Agent? What is a MAS? Orchestration & first MAS example).citeturn4search1

**Goals**  

- Internalize the **anatomy of an agent** (model, tools, memory).citeturn4search1  
- Understand the definition of a **multi-agent system** and the two orchestration approaches: workflow vs autonomous.citeturn4search1  
- Become familiar with the **haiku poet + critic** example and round-robin orchestration.citeturn4search1

**Key concepts**  

- Agent action–perception loop (Figure 1.6).citeturn4search1  
- Agent components (Figure 1.5) and MAS orchestration overview (Figure 1.7).citeturn4search1

**Hands-on exercise (individual or pair)**  

- Follow the “Building Your First Multi-Agent System” section in Chapter 1 to implement the **poet + critic** round-robin MAS using `picoagents`.citeturn4search1

**Group activity (session)**  

- Inspect an execution trace from your poet–critic system. Identify:  
  - where reasoning happens,  
  - where tools would fit if you added them,  
  - how termination is decided.

---

## Week 3 — Multi-Agent Patterns I: Workflow Patterns

**Reading**  

- Chapter 2: Sections 2.1–2.2 (Taxonomy; Sequential, Conditional, Parallel workflows).citeturn4search1

**Goals**  

- Understand the **autonomy spectrum** from explicit workflows to autonomous patterns (Figure 2.1).citeturn4search1  
- Learn the three main **workflow patterns**: sequential, conditional, parallel.citeturn4search1  
- Map one of your own real-world processes to a workflow graph.

**Key concepts**  

- Nodes and edges; graphs as computational workflows (Sections 2.2, 6.1–6.3).citeturn4search1  
- Sequential workflow example (Figure 2.2).citeturn4search1

**Hands-on exercise**  

- For a task like “summarize recent incident reports and produce a weekly report”, design a **sequential workflow**: Ingest → Classify → Summarize → Format.

**Group activity**  

- As a group, draw your workflow on a board and label each step as:  
  - human-only,  
  - agent-only, or  
  - mixed human+agent.

---

## Week 4 — Multi-Agent Patterns II: Autonomous Patterns

**Reading**  

- Chapter 2: Sections 2.3–2.6 (Autonomous patterns; pattern selection; task management).citeturn4search1

**Goals**  

- Understand **plan-based**, **handoff**, and **conversation-driven (group chat)** patterns.citeturn4search1  
- Learn the trade-offs between deterministic workflows and emergent autonomous coordination.citeturn4search1  
- Understand when to pick each pattern (Table 2.2, Section 2.4).citeturn4search1

**Key concepts**  

- Plan-based orchestration (Figure 2.6).  
- Handoff pattern (Figure 2.7).  
- Conversation-driven patterns: round-robin vs AI-driven turn taking (Figures 2.8–2.10).citeturn4search1

**Hands-on exercise**  

- Implement both:  
  - a **round-robin** conversation pattern; and  
  - an **AI-driven** conversation pattern using `AIOrchestrator` (Chapter 7 mapping).citeturn4search1

**Group activity**  

- Using the decision framework in Section 1.7 (Figure 1.8), classify 3–5 of your own scenarios into:  
  - “model only”,  
  - “single agent”,  
  - “workflow MAS”,  
  - “autonomous MAS”.citeturn4search1

---

## Week 5 — UX Principles for Multi-Agent Systems

**Reading**  

- Chapter 3 in full (UX principles, capability discovery, cost-aware delegation, observability, interruptibility).citeturn4search1

**Goals**  

- Understand the shift from **interface design** to **delegation design**.citeturn4search1  
- Learn the four core UX principles: capability discovery, cost-aware delegation, observability & provenance, interruptibility (Figure 3.3).citeturn4search1  
- Recognize the “jagged frontier” of reliability and its UX implications (Figure 3.2).citeturn4search1

**Hands-on exercise**  

- Choose a MAS prototype (e.g., poet–critic or a simple research workflow) and:  
  - add **basic activity logging and streaming**;  
  - expose at least one **user control** (e.g., “Stop”/“Cancel”).

**Group activity**  

- Critique a well-known agentic UX (Copilot, ChatGPT plugins, etc.) from the perspective of the four UX principles.

---

## Week 6 — Building Agents from Scratch I: Agent Anatomy

**Reading**  

- Chapter 4: Sections 4.1–4.7 (design principles, execution loop, model client, tools, memory).citeturn4search1

**Goals**  

- Understand the **agent execution loop** and why an **async-first** design matters.citeturn4search1  
- Implement an agent with:  
  - an LLM model client,  
  - at least one tool,  
  - short-term memory via message history.

**Key concepts**  

- Agent interface: `Agent(model, tools, memory)`.citeturn4search1  
- Structured output and tool calling (Sections 4.5–4.6).citeturn4search1  
- Short-term vs long-term memory, RAG introduction (Section 4.7).citeturn4search1

**Hands-on exercise**  

- Build an agent that:  
  - answers questions,  
  - calls a simple Python function tool,  
  - uses message history to resolve pronouns or follow-up questions.

**Group activity**  

- Compare implementations and discuss:  
  - how you structured prompts,  
  - where structured output improved reliability,  
  - what you logged for debugging.

---

## Week 7 — Building Agents from Scratch II: Middleware, Memory & HITL

**Reading**  

- Chapter 4: Sections 4.8–4.13 (agent-managed memory, middleware, OpenTelemetry, human-in-the-loop).citeturn4search1

**Goals**  

- Understand **application-managed vs agent-managed memory** and when to use each.citeturn4search1  
- Learn how middleware enables **control and observability** (Section 4.9–4.10).citeturn4search1  
- Implement **tool approval** and basic human-in-the-loop (Section 4.13).citeturn4search1

**Hands-on exercise**  

- Extend last week’s agent to:  
  - use a simple long-term memory store (e.g., file- or list-based),  
  - add a middleware that logs each model call and tool call,  
  - require explicit approval for at least one “risky” tool.

**Group activity**  

- Review your middleware and memory strategies. Discuss the trade-offs between automatic vs explicit memory writes and between light vs heavy logging.

---

## Week 8 — Computer-Use Agents and Interface Grounding

**Reading**  

- Chapter 5 in full (anatomy of computer-use agents, interface representations, action spaces, challenges).citeturn4search1

**Goals**  

- Understand when **code/APIs are not enough** and UI automation is required.citeturn4search1  
- Learn the three interface representation strategies: text-based, image-based, hybrid (Section 5.3).citeturn4search1  
- Understand the action space and observation loop for GUI agents (Section 5.5).citeturn4search1

**Hands-on exercise**  

- Implement a _minimal_ browser-automation agent that:  
  - opens a page,  
  - performs one or two deterministic interactions (e.g., search, click a result).

**Group activity**  

- Identify concrete tasks in your environment (internal tools, portals) where computer-use agents would unlock value that API-based tools cannot.

---

## Week 9 — Multi-Agent Workflows & Orchestration from Scratch

**Reading**  

- Chapter 6 in full (workflows as computational graphs, edges, runner, checkpointing).citeturn4search1  
- Chapter 7: Sections 7.1–7.3 (orchestrator loop, termination, round-robin).citeturn4search1

**Goals**  

- Implement **workflow-based orchestration** using steps and edges.citeturn4search1  
- Understand **checkpointing** and why it matters for long-running workflows (Section 6.7).citeturn4search1  
- Implement a **round-robin orchestrator** over multiple agents.

**Hands-on exercise**  

- Build a workflow MAS with 3–4 steps, for example:  
  - Search → Analyze → Draft → Review.  
- Add at least one **conditional edge** (e.g., if quality < threshold, go back to Analyze).citeturn4search1

**Group activity**  

- Run each team’s workflow on the same task and compare:  
  - trace length (number of steps),  
  - failure modes,  
  - where checkpointing helped.

---

## Week 10 — Evaluation and Optimization of MAS

**Reading**  

- Chapter 10 in full (evaluating multi-agent systems).citeturn4search1  
- Chapter 11: Sections 11.2–11.3 (what to optimize, failure modes).citeturn4search1

**Goals**  

- Understand **trajectory-based evaluation** and multi-agent trajectories.citeturn4search1  
- Learn how to design an **evaluation suite** and when to use LLM-as-judge (Sections 10.4–10.6).citeturn4search1  
- Study common **failure modes** of MAS and treat them as optimization opportunities (Section 11.3).citeturn4search1

**Hands-on exercise**  

- For your Week 9 workflow:  
  - create a small **task suite** (e.g., 5 tasks),  
  - define simple **success criteria**,  
  - implement a **judge** (LLM-as-judge or rule-based) to score outputs.

**Group activity**  

- Compare evaluation results; categorize failures using the failure modes in Section 11.3 (e.g., “wrong pattern”, “no good tools”, “no evals”).citeturn4search1

---

## Week 11 — Distributed Agents and Protocols

**Reading**  

- Chapter 12 in full (Model Context Protocol (MCP), Agent-to-Agent protocol (A2A), security).citeturn4search1

**Goals**  

- Understand **distributed agent requirements** (Section 12.1).citeturn4search1  
- Learn MCP’s architecture and core concepts (Sections 12.2.1–12.2.3).citeturn4search1  
- Understand A2A and when distributed protocols are necessary vs over-engineering (Section 12.5).citeturn4search1

**Hands-on exercise**  

- Run a simple example using an MCP server/tool (e.g., a filesystem tool) and connect an agent to it.citeturn4search1

**Group activity**  

- For your organization, brainstorm scenarios where **distributed agents** (across services or org boundaries) are truly required vs when a single-process MAS is sufficient.

---

## Week 12 — Ethics, Responsible AI, and Capstone Synthesis

**Reading**  

- Chapter 13 in full (ethics, societal challenges, security, defense through middleware).citeturn4search1  
- Chapter 14 or 15 (pick one case study most relevant to your domain: unstructured-data Q&A or software engineering agent).citeturn4search1  
- Epilogue (for forward-looking view).citeturn4search1

**Goals**  

- Understand **agentic ethics**, agentic noise, platform imbalance, and emergent risks (Section 13.3).citeturn4search1  
- Learn security patterns for agents that can act (Section 13.4, “Rule of Two”, middleware defenses).citeturn4search1  
- Synthesize concepts from all previous weeks into a **capstone MAS design**.

**Capstone project (team-based)**  
Design and (at least partially) implement a **multi-agent system** that includes:

- 3+ agents with clearly differentiated roles.  
- At least one **tool per agent**.  
- One **orchestration pattern** (workflow _or_ autonomous); hybrid is a plus.  
- Short-term memory and at least a minimal long-term memory component.  
- Basic UX surface with:  
  - streaming logs,  
  - at least one interrupt mechanism,  
  - minimal evaluation harness (success criteria + manual or LLM-as-judge scoring).

**Group activity (Week 12 session)**  

- Each team presents:  
  - the **problem** they chose,  
  - the **architecture** (agents, tools, orchestration pattern),  
  - key **trade-offs** they made (e.g., why workflow vs autonomous),  
  - evaluation results and main failure modes,  
  - how they applied **UX and responsible AI principles**.

---

## Ongoing Practices Throughout the 12 Weeks

You can reinforce learning by repeating these each week:

- **Concept mapping** – After each chapter, individually sketch a diagram of the main concepts (e.g., Week 4: autonomy spectrum and patterns; Week 6: agent execution loop).
- **Pattern identification** – For every new example you see (in the book or your work), ask:  
  - which **orchestration pattern** is this?  
  - what are the **task characteristics** (planning, diverse expertise, context, adaptation)?
- **Retrospective** – End each weekly session with a 5–10 minute retro:  
  - what concept is clear?  
  - what is still confusing?  
  - what should we demo or implement next week to clarify it?

This markdown file is ready to be used as a shared syllabus for your study group or as the basis for a repo `README.md`.
