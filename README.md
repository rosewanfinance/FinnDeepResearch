# Multi-Agent Financial Research — Skill & Workflow Prototype

A lightweight prototype demonstrating how a professional financial-research workflow can be
decomposed into **reusable Skills** and orchestrated by a **Research Director**.

This is an **architecture-first** prototype: the primary artifacts are Markdown definitions of
capabilities, a workflow/orchestration definition, and a small set of native subagents. It is
deliberately *not* a production application (no UI, DB, agent framework, or API).

> Full context: [`proposal.md`](proposal.md).

## Core idea

> **Skills describe capabilities. The Director determines how those capabilities are composed.**

Instead of one giant prompt, the system:

1. Decomposes an investment question into sub-questions (**research planning**).
2. Delegates each to a specialized capability (**fundamentals, industry/competitive,
   financial/valuation**).
3. Evaluates the evidence (**evidence analysis**) and, where confidence is low, recurses deeper.
4. Challenges the emerging thesis (**bear case**) before synthesizing a final memo.

```text
                         User Question
                               |
                               v
                     +-------------------+
                     | Research Director |
                     +---------+---------+
                               |
                     Research Planning
                               |
          +--------------------+--------------------+
          |                    |                    |
          v                    v                    v
   Fundamental           Industry / TAM       Competitive
    Research               Research            Intelligence
          |                    |                    |
          +--------------------+--------------------+
                               |
                               v
                       Evidence Synthesis
                               |
                    +----------+----------+
                    |                     |
                    v                     v
              Valuation Skill       Bear Case Skill
                    |                     |
                    +----------+----------+
                               |
                               v
                     Research Director
                               |
                               v
                    Investment Research Memo
```

## Evidence-first model

Prose is never the fundamental artifact. Findings move up a traceable chain:

```text
Source → Observation → Claim → Interpretation → Investment Thesis
```

This separation lets the Director locate exactly *where* an argument is weak.

## Directory map

```text
finn_research/
├── README.md                       ← this file
├── proposal.md                     ← the source proposal
├── skills/                         ← reusable capability methodology (the "what/how")
│   ├── research-planning.md
│   ├── fundamental-research.md
│   ├── industry-competitive-research.md
│   ├── financial-valuation.md
│   ├── evidence-analysis.md
│   └── bear-case.md
├── .claude/agents/                 ← native subagents (the "who"); reference their skill
│   ├── fundamental-research.md
│   ├── industry-competitive-research.md
│   ├── financial-valuation.md
│   ├── evidence-analysis.md
│   └── bear-case.md
├── workflows/
│   └── deep-equity-research.md     ← orchestration definition + shared schemas
├── orchestration/
│   └── director.md                 ← the Director's operating manual
├── examples/
│   ├── nvidia-ai-infrastructure/   ← benchmark question + expected artifacts (TAM-growth angle)
│   └── amd-ai-accelerators/        ← benchmark question + expected artifacts (competitive-share angle)
└── evaluation/
    └── research-quality.md         ← how to judge research quality
```

## Relationship: Skills vs. subagents

- **`skills/*.md`** — reusable *methodology* (purpose, inputs, outputs, constraints, reasoning
  mandate, evidence requirements, handoff format, stopping conditions). Tool-agnostic.
- **`.claude/agents/*.md`** — thin, spawnable subagents (frontmatter + role) that load the matching
  skill and enforce the output contract. The Director spawns these via the Agent tool.

Research **planning** is the Director's own job (no subagent); `skills/research-planning.md` is its
methodology reference.

## How to run

There is no runner or script — the Director is the main Claude Code session.

1. Start Claude Code in this directory.
2. Instruct it: *"Act as the Research Director (see `orchestration/director.md`) and run the deep
   equity research workflow (`workflows/deep-equity-research.md`) on the benchmark question in
   `examples/nvidia-ai-infrastructure/question.md`."*
3. The Director plans, spawns subagents, deepens where evidence is weak, runs the bear case, and
   writes artifacts (plan, trace, findings, audit, memo) into
   `examples/nvidia-ai-infrastructure/output/`.

Subagent `model` is left to inherit from the session; the adversarial agents (evidence-analysis,
bear-case) can be bumped to a higher tier later if depth matters more than cost.

## What this demonstrates (interview narrative)

1. **AI capability design** — decomposing research into reusable capabilities, not one assistant.
2. **Agent orchestration** — a Director decides *which* capabilities and *how deep*.
3. **Financial workflow understanding** — modeled on a real equity-research process.
4. **Ecosystem thinking** — external data, research, and tools can be represented as Skills.
5. **AI evaluation** — grading claims, evidence, and contradictions, not prose aesthetics.
6. **Product thinking** — the goal is a reusable workflow, not a chatbot answer.

## What this is not

No autonomous trading agent, no attempt to replace analysts, no recommendation engine, no
production data platform, no custom model training, no frontend, no large-scale infra, and no
dozens of shallow Skills (see proposal §15).
