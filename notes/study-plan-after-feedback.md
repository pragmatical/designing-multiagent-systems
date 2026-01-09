# 12-Week Multi-Agent Systems Study Plan (Inclusive / Mixed-Experience Version)

Using **Victor Dibia’s _Designing Multi-Agent Systems_** as the primary material.

This is an alternative version of the study plan in [notes/study-plan.md](study-plan.md), designed so that:

- Sessions are inclusive and valuable even if some participants **fall behind on the reading**.
- Group activities **minimize dependency on prior expertise**.
- Everyone can contribute meaningfully (design, critique, risk, UX, evaluation), not just the strongest coders.

---

## How each session runs (60–90 minutes)

Use the same structure every week to minimize “context debt” and make facilitation easier.

- **5 min — Arrival + agenda**: state today’s outcome (a shared artifact) and how decisions will be made.
- **10 min — “Everyone can participate” primer**: one person gives a short recap using the standing prompt.
- **25–35 min — Small-group exercise** (3–5 people): produce a concrete artifact.
- **10–20 min — Share-outs**: each group shares 1 insight + 1 open question.
- **5 min — Close**: quick retro + assign light prep (optional).

### Standing recap prompt (works even without reading)

Whoever recaps answers:

- What is the **problem** this chapter/week addresses?
- What is the **core idea** in one sentence?
- What is a **real example** (work or personal)?
- What is the **failure mode** if we misuse it?

### Participant types (use these in every exercise)

Instead of assigning roles, assume your group includes a mix of participant types. When you do an exercise, explicitly collect input from **at least 3 different types** so the artifact is useful to everyone.

- **Newcomer / catching up**: needs clear definitions, examples, and a “why this matters” summary.
- **Hands-on builder**: turns ideas into steps, interfaces, and minimal implementations.
- **Domain expert**: grounds scenarios in real constraints, business rules, and edge cases.
- **Product / UX**: focuses on user goals, delegation design, observability, and control.
- **Risk / security / compliance minded**: surfaces misuse, safety controls, data boundaries, and approvals.
- **Evaluator / QA**: defines measurable success criteria, test cases, and failure categorization.

### Tiered participation (choose your depth)

Every week has three lanes so people can participate without feeling behind.

- **Baseline (everyone)**: discussion + artifact; no code required.
- **Applied (optional)**: adapt the artifact to a real scenario or a sample in the repo.
- **Stretch (optional)**: implement or extend something in code.

---

## Week 1 — Foundations I: Why Multi-Agent Systems?

**Reading**: Preface (skim), Chapter 1: Sections 1.1–1.4

**Goals**

- Distinguish when a **model**, **single agent**, or **multi-agent system (MAS)** is the right tool.
- Recognize task characteristics that push you toward agentic systems (planning, tools, context, adaptation).
- Build a shared vocabulary for discussing “agentic” work in plain language.

**Key concepts**

- Task complexity spectrum: model → agent → MAS.
- Agent capabilities: reasoning, acting (tools), communicating, adapting.
- Common failure mode: prompt-only solutions break when they need tools, fresh data, or robust planning.

**Session outcome**: A shared list of tasks mapped to **model → agent → MAS**.

**Baseline group exercise (low-dependency)**

- Pick 2–3 tasks anyone can understand (e.g., travel planning, weekly status summary, incident triage).
- For each task, fill a 6-box template:
  - Inputs / Outputs
  - Where fresh data is needed
  - Where planning is needed
  - Where multiple skills are needed
  - Likely failure modes
  - Best fit: model / agent / MAS (and why)

**Stretch (optional)**: build a prompt-only “agent” and document where it fails.

---

## Week 2 — Foundations II: Agent and MAS Architecture

**Reading**: Chapter 1: Sections 1.4–1.9

**Goals**

- Identify the core components of an agent: **model, tools, memory, control loop**.
- Understand what makes a system “multi-agent” and how orchestration affects reliability and cost.
- Practice reading an interaction as an **execution trace** (what happened, why, and when it stops).

**Key concepts**

- Agent action–perception loop and termination.
- Orchestration basics: round-robin vs decision-based turn taking.
- Traces/logs as a shared debugging surface for technical and non-technical participants.

**Session outcome**: A shared “agent anatomy” diagram and a minimal orchestration sketch.

**Baseline group exercise (low-dependency)**

- Make one diagram together:
  - Model, tools, memory, control loop, termination.
- Then do a **role-play trace** (no code):
  - Person A = “poet”, Person B = “critic”, Person C = “orchestrator”.
  - Run 3 turns and write down: messages, decisions, stop condition.

**Applied (optional)**: inspect an existing trace from someone’s implementation.

---

## Week 3 — Multi-Agent Patterns I: Workflow Patterns

**Reading**: Chapter 2: Sections 2.1–2.2

**Goals**

- Translate a real task into a simple, testable workflow.
- Understand the difference between **sequential**, **conditional**, and **parallel** steps.
- Make “done” and “quality checks” explicit in the workflow.

**Key concepts**

- Workflows as graphs: nodes (steps) and edges (transitions).
- Determinism and debuggability as benefits of workflows.
- Validation steps as a practical reliability tool.

**Session outcome**: One workflow graph the group agrees is clear and testable.

**Baseline group exercise (low-dependency)**

- Start with a plain-language task statement.
- Convert it into a workflow with:
  - 4–6 steps (verbs only)
  - inputs/outputs per step
  - at least 1 validation/check step
- Everyone can contribute by suggesting steps, checks, or edge cases.

**Stretch (optional)**: implement the workflow in the repo framework of choice.

---

## Week 4 — Multi-Agent Patterns II: Autonomous Patterns

**Reading**: Chapter 2: Sections 2.3–2.6

**Goals**

- Compare autonomous coordination patterns and choose one for a scenario.
- Understand trade-offs between explicit workflows and emergent coordination.
- Make safety, cost, and clarity constraints first-class in pattern selection.

**Key concepts**

- Autonomy spectrum (workflow → semi-autonomous → autonomous).
- Patterns: plan-based, handoff, conversation/group-chat.
- Pattern selection is a design decision: wrong pattern is a common failure mode.

**Session outcome**: A pattern-selection decision record for 2 scenarios.

**Baseline group exercise (low-dependency)**

- Use a “pattern picker” matrix:
  - Determinism needed? (low/med/high)
  - Task clarity? (low/med/high)
  - Safety constraints? (low/med/high)
  - Cost sensitivity? (low/med/high)
- For two scenarios, choose: workflow vs plan-based vs handoff vs group-chat.
- Ensure you capture:
  - 2 risks (from a risk/security/compliance perspective), and
  - a plain-language summary (from a newcomer perspective).

---

## Week 5 — UX Principles for Multi-Agent Systems

**Reading**: Chapter 3

**Goals**

- Treat agent UX as **delegation design**, not just interface design.
- Identify what users need to trust and control an agentic system.
- Produce actionable UX improvements that reduce confusion and risk.

**Key concepts**

- Capability discovery: what the system can/can’t do.
- Cost-aware delegation: time/money trade-offs.
- Observability & provenance: “show your work.”
- Interruptibility: stop, pause, undo, and recover.

**Session outcome**: A usability review checklist for agentic UX.

**Baseline group exercise (low-dependency)**

- Pick any familiar product/flow (even non-AI).
- Score it against the four principles:
  - capability discovery
  - cost-aware delegation
  - observability & provenance
  - interruptibility
- Produce one “quick win” improvement for each principle.

**Stretch (optional)**: add minimal logging + cancel/stop control to a sample agent.

---

## Week 6 — Building Agents from Scratch I: Agent Anatomy

**Reading**: Chapter 4: Sections 4.1–4.7

**Goals**

- Understand the execution loop: how an agent decides, acts, and updates state.
- Design tools with clear inputs/outputs and failure modes.
- Recognize when structured outputs make systems more reliable.

**Key concepts**

- Tool calling as a reliability and capability upgrade over prompting.
- Structured output (schemas) to reduce ambiguity.
- Memory basics: short-term (conversation) vs long-term (knowledge/context).

**Session outcome**: A shared implementation-agnostic agent execution loop.

**Baseline group exercise (low-dependency)**

- Build a **tool card deck** (index-card style, in a doc):
  - tool name, input, output, failure modes, safety notes
- Each participant contributes 1 tool card (real or hypothetical).
- As a group, decide where the tool fits in the execution loop.

**Stretch (optional)**: implement 1 tool + structured output.

---

## Week 7 — Building Agents from Scratch II: Middleware, Memory & HITL

**Reading**: Chapter 4: Sections 4.8–4.13

**Goals**

- Decide what must be logged/observed to debug and govern agents.
- Define when to require human approval (human-in-the-loop).
- Make memory policies explicit: what gets stored, when, and why.

**Key concepts**

- Middleware as a control layer (logging, policy, safety checks).
- Tool approval for risky actions.
- Memory write strategies: automatic vs explicit; safe defaults.

**Session outcome**: A safety/observability “minimum viable controls” checklist.

**Baseline group exercise (low-dependency)**

- For a chosen agent, decide:
  - what to log (model calls, tool calls, outcomes)
  - what requires approval (high-risk actions)
  - what should be stored (memory) and when
- Write one policy: “When X happens, require Y approval and log Z.”

---

## Week 8 — Computer-Use Agents and Interface Grounding

**Reading**: Chapter 5

**Goals**

- Determine when UI automation is justified vs APIs/tools.
- Understand the observation/action loop for computer-use agents.
- Identify fragility and safety concerns early.

**Key concepts**

- Interface representations: text-based, image-based, hybrid.
- Action spaces: clicks, typing, navigation, forms.
- Grounding and robustness: what the agent “sees” must match reality.

**Session outcome**: A “UI agent feasibility” rubric.

**Baseline group exercise (low-dependency)**

- Choose 2 tasks:
  - one that should use APIs
  - one that might require UI automation
- For each, fill a rubric:
  - observability (what can the agent see?)
  - action space (what can it do?)
  - fragility (what breaks?)
  - safety (what’s risky?)
  - fallback plan (what if UI changes?)

---

## Week 9 — Multi-Agent Workflows & Orchestration from Scratch

**Reading**: Chapter 6; Chapter 7: Sections 7.1–7.3

**Goals**

- Turn a workflow graph into an executable spec with checkpoints and recovery.
- Define termination and recovery in a way the whole group can review.
- Compare orchestration options by how they behave under failure.

**Key concepts**

- Workflow runners and checkpoints for long tasks.
- Termination conditions: what “done” means.
- Recovery strategies: retry, fallback, human escalation.

**Session outcome**: A testable workflow spec plus one termination rule.

**Baseline group exercise (low-dependency)**

- Using last week’s workflow graph, add:
  - a checkpoint policy (when to save state)
  - a termination rule (what “done” means)
  - a recovery rule (what to do on failure)

---

## Week 10 — Evaluation and Optimization of MAS

**Reading**: Chapter 10; Chapter 11: Sections 11.2–11.3

**Goals**

- Define success criteria that are measurable and aligned to user value.
- Build a small evaluation suite that enables iteration.
- Use failure modes to decide what to fix first.

**Key concepts**

- Task suites and scoring rubrics.
- Trajectories/traces as evaluation artifacts (not just final outputs).
- Judges: rule-based checks vs LLM-as-judge; trade-offs and safeguards.

**Session outcome**: A 5-task evaluation suite and scoring rubric.

**Baseline group exercise (low-dependency)**

- Brainstorm 10 candidate tasks; pick 5 that are:
  - representative
  - easy to understand
  - measurable
- Define success criteria that don’t require ML expertise:
  - correctness checks, completeness checks, format checks, and a 1–5 usefulness score.

**Stretch (optional)**: implement LLM-as-judge and compare with rule-based scoring.

---

## Week 11 — Distributed Agents and Protocols

**Reading**: Chapter 12

**Goals**

- Decide when distribution is necessary vs over-engineering.
- Identify trust boundaries and what data/actions must be constrained.
- Understand how protocols like MCP/A2A help with interoperability and separation.

**Key concepts**

- Distributed requirements: ownership boundaries, security, network constraints.
- Tool servers and standardized interfaces (MCP) and agent-to-agent coordination (A2A).
- Security posture: least privilege, approvals, and auditing across boundaries.

**Session outcome**: A boundary diagram showing when distribution is warranted.

**Baseline group exercise (low-dependency)**

- Draw a system boundary diagram:
  - what runs in one process
  - what must be separate (security, ownership, network)
  - what data cannot cross boundaries
- Decide whether MCP/A2A is justified for one scenario.

---

## Week 12 — Ethics, Responsible AI, and Capstone Synthesis

**Reading**: Chapter 13 + (Chapter 14 or 15)

**Goals**

- Identify ethical and safety risks unique to agents that can act.
- Apply practical defenses (policy, middleware, approvals, monitoring).
- Synthesize the course into a capstone design that non-experts can review.

**Key concepts**

- Agentic risk: emergent behavior, misuse, automation bias, “agentic noise”.
- Defense in depth: policy + logging + approvals + least privilege.
- Capstone as a coherent design: agents, tools, orchestration, UX controls, evaluation.

**Session outcome**: A capstone design that’s reviewable by non-experts.

**Baseline group exercise (low-dependency)**

- Create a “capstone poster” (one page):
  - problem statement (plain language)
  - agents + roles
  - tools + approvals
  - orchestration choice + why
  - evaluation plan
  - top 3 risks + mitigations
- Presentations are scored on clarity, not code.

**Stretch (optional)**: partial implementation + demo trace.

---

## Ongoing practices (inclusive by default)

- **Jargon jar**: whenever someone uses jargon, define it once in a shared glossary.
- **One-minute teach-back**: end each session with one volunteer summarizing today’s concept in plain language.
- **Artifact-first**: every session produces something shareable (diagram, rubric, checklist, workflow spec) so absentees can catch up without reading everything.
