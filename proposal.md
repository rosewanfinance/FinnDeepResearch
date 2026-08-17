Yes. I would position this as a **research-system prototype**, not an “AI agent product.” The key is to demonstrate that the candidate understands how to **design reusable financial research capabilities and orchestrate them into a deep-research workflow**.

Here is the proposal I would give to Claude Code.

# Multi-Agent Financial Research Skill & Workflow Prototype

## 1. Objective

Build a lightweight prototype demonstrating how a professional financial research workflow can be decomposed into reusable AI Skills and orchestrated by a Research Director.

The goal is **not** to build a complete autonomous financial research agent or a production-ready application.

Instead, the prototype should demonstrate three capabilities:

1. **Financial research expertise can be encoded as reusable Skills.**
2. **Multiple specialized agents can be orchestrated to investigate different dimensions of an investment question.**
3. **A Director agent can dynamically plan, delegate, evaluate, and deepen research rather than following a rigid predefined sequence.**

The entire prototype should remain lightweight and reproducible, with the primary artifacts being Markdown-based Skill definitions, workflow/orchestration definitions, and a small amount of glue code where necessary.

---

# 2. Product Concept

The prototype should simulate a small professional equity-research desk.

A user provides a research question such as:

> "Is NVIDIA's current valuation justified by the expected growth of AI infrastructure spending over the next three years?"

Instead of asking one LLM to answer the question, the system creates a research plan and delegates different questions to specialized research capabilities.

Conceptually:

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
                    Investment Research
                           Memo
```

The important distinction is that the Director should **not simply execute this diagram from top to bottom**.

The diagram represents the available capabilities.

The Director should decide:

* which questions need investigation;
* which Skills should be invoked;
* which research tasks can run in parallel;
* which findings require deeper investigation;
* which claims lack sufficient evidence;
* when a research branch can stop;
* when a new sub-question should be created;
* when the final synthesis is sufficiently supported.

---

# 3. Design Principle

The core principle is:

> **Skills describe capabilities. The Director determines how those capabilities are composed.**

Do not create one giant prompt containing the entire research process.

Instead, separate:

### Skills

Reusable research capabilities such as:

* company fundamentals;
* financial statement analysis;
* industry analysis;
* competitive intelligence;
* event/news analysis;
* valuation;
* evidence verification;
* bear-case analysis.

### Workflow / Orchestration

The workflow describes how these capabilities may be combined.

The Director should be able to dynamically construct a research plan based on the question.

For example:

```text
Research Question
       |
       v
Decompose into Research Questions
       |
       v
Assign Skills
       |
       v
Parallel Investigation
       |
       v
Evaluate Evidence
       |
       +---- weak evidence ---> deeper research
       |
       +---- contradictory ----> investigate conflict
       |
       +---- sufficient -------> continue
       |
       v
Synthesize Thesis
       |
       v
Challenge Thesis
       |
       v
Final Research Memo
```

The orchestration logic should live in the workflow/orchestration layer rather than being encoded as a fixed sequence inside every Skill.

---

# 4. Scope

Keep the initial prototype deliberately narrow.

### Domain

Public equity research.

### Research questions

Focus on questions involving:

* company growth;
* industry growth;
* competitive position;
* financial performance;
* valuation;
* catalysts;
* risks;
* investment thesis.

### Initial benchmark question

Use one challenging research question as the primary demonstration:

> "Is NVIDIA's current valuation justified by the expected growth of AI infrastructure spending over the next three years?"

This question is intentionally selected because it requires:

* company research;
* industry research;
* hyperscaler spending analysis;
* competitive analysis;
* financial analysis;
* valuation;
* scenario analysis;
* evidence validation;
* bear-case analysis.

It therefore demonstrates why multi-agent research is useful.

---

# 5. Proposed Skills

Do not build too many Skills.

The prototype should contain approximately 5–7 high-quality Skills rather than 20 shallow ones.

## Skill 1 — Research Planning

Purpose:

Convert an investment question into a structured research plan.

Responsibilities:

* identify the main investment thesis;
* decompose it into research questions;
* identify dependencies;
* identify required evidence;
* identify relevant Skills;
* identify questions that require quantitative analysis;
* identify potentially controversial assumptions.

Output should be structured rather than prose-heavy.

Example conceptual output:

```yaml
research_question:
  ...

sub_questions:
  - id: revenue_growth
    question: ...
    required_capabilities:
      - fundamentals
      - industry
    priority: high

  - id: competitive_position
    question: ...
    required_capabilities:
      - industry
      - competitive_intelligence
    priority: high

  - id: valuation
    question: ...
    required_capabilities:
      - financials
      - valuation
    priority: high
```

The exact schema can be designed during implementation.

---

## Skill 2 — Fundamental Research

Purpose:

Analyze the company's business and fundamental drivers.

Focus on:

* revenue segmentation;
* volume / price / mix;
* margins;
* operating leverage;
* cash flow;
* capital expenditure;
* business segments;
* customer concentration;
* fundamental growth drivers.

The Skill should distinguish between:

* observed facts;
* management claims;
* analyst assumptions;
* inferred conclusions.

---

## Skill 3 — Industry & Competitive Research

Purpose:

Understand the external environment surrounding the company.

Analyze:

* TAM;
* industry growth;
* supply/demand;
* market share;
* competitors;
* substitutes;
* pricing;
* technology transitions;
* customer behavior;
* ecosystem effects.

The output should answer:

> Is the company's growth primarily driven by market growth, market-share gain, or both?

For NVIDIA, for example, this Skill should investigate the broader AI infrastructure ecosystem rather than simply collecting NVIDIA-related information.

---

## Skill 4 — Financial & Valuation Analysis

Purpose:

Translate research findings into quantitative financial implications.

Capabilities may include:

* revenue growth analysis;
* margin analysis;
* cash-flow analysis;
* historical multiples;
* DCF;
* P/E / EV/Sales / EV/EBITDA;
* bull/base/bear scenarios;
* sensitivity analysis.

A critical requirement:

Every important valuation assumption should have an explicit origin.

For example:

```text
Revenue CAGR
    |
    +-- Historical evidence
    +-- Industry forecast
    +-- Company guidance
    +-- Analyst assumption
```

The Skill should avoid producing a precise valuation number without explaining where the assumptions came from.

---

## Skill 5 — Evidence & Contradiction Analysis

Purpose:

Evaluate the quality of research evidence.

Every important claim should ideally have:

```text
Claim
Source
Source Type
Publication Date
Supporting Evidence
Confidence
```

The Skill should detect:

* unsupported claims;
* weak sources;
* outdated information;
* contradictory evidence;
* claims supported only by management commentary;
* conclusions that go beyond the available evidence.

This Skill is important because the goal is not simply to produce a convincing report.

The goal is to produce a **defensible research conclusion**.

---

## Skill 6 — Bear Case / Devil's Advocate

Purpose:

Actively challenge the emerging investment thesis.

Input:

* current thesis;
* supporting evidence;
* assumptions;
* valuation;
* identified risks.

The Skill should ask:

* What if the core assumption is wrong?
* What evidence contradicts the thesis?
* What could cause growth to disappoint?
* What competitive threat is underestimated?
* What is already priced into the valuation?
* Which assumption has the highest sensitivity?
* What observation would invalidate the thesis?

The output should identify:

```text
Thesis
    ↓
Critical Assumption
    ↓
Counter Evidence
    ↓
Failure Scenario
    ↓
Potential Impact
    ↓
What Should Be Monitored
```

---

# 6. Evidence-First Research Model

The system should avoid treating generated prose as the fundamental research artifact.

Instead, use a structured evidence model.

Conceptually:

```text
Source
   |
   v
Observation
   |
   v
Claim
   |
   v
Interpretation
   |
   v
Investment Thesis
```

For example:

```text
Source:
Company filing

Observation:
Data-center revenue increased X%.

        ↓

Claim:
Data-center demand remains strong.

        ↓

Interpretation:
AI infrastructure spending is supporting revenue growth.

        ↓

Thesis:
Near-term growth can remain elevated.
```

This separation is important because the Director can then identify exactly where an argument is weak.

---

# 7. Research Director

The Director is the central orchestration component.

It should not contain all financial research knowledge itself.

Its responsibilities are:

### 7.1 Understand the research question

Determine:

* what the user actually wants to know;
* what decision the research should support;
* what dimensions need investigation.

### 7.2 Build a research plan

Select appropriate Skills and create research tasks.

### 7.3 Delegate

Assign tasks to specialized agents using the appropriate Skill.

### 7.4 Parallelize

Independent questions should be investigated concurrently where practical.

Example:

```text
                  Director
                     |
       +-------------+-------------+
       |             |             |
       v             v             v
  Fundamentals   Industry      Competition
```

### 7.5 Evaluate intermediate results

The Director should inspect:

* evidence quality;
* confidence;
* contradictions;
* unresolved questions;
* importance to the thesis.

### 7.6 Decide whether to deepen research

This is one of the most important behaviors.

For example:

```text
Importance = High
Confidence = Low
        |
        v
    Deep Dive
```

Whereas:

```text
Importance = Low
Confidence = High
        |
        v
       Stop
```

### 7.7 Synthesize

Only after the major research branches have produced sufficient evidence should the Director construct the final thesis.

### 7.8 Challenge

Invoke the Bear Case capability before finalization.

### 7.9 Produce the final research package

The final result should contain:

1. Executive Summary
2. Investment Thesis
3. Key Evidence
4. Fundamental Analysis
5. Industry / Competitive Analysis
6. Valuation
7. Bull / Base / Bear Cases
8. Key Risks
9. Contradictory Evidence
10. Key Assumptions
11. Monitoring Indicators
12. Sources

---

# 8. Dynamic Research Depth

A major differentiator of this prototype should be **adaptive research depth**.

Do not define:

```text
Step 1 → Step 2 → Step 3 → Step 4
```

as the only workflow.

Instead, allow:

```text
Question
   |
   v
Initial Investigation
   |
   v
Is evidence sufficient?
   |
   +---- YES ----> Continue
   |
   +---- NO -----> Generate deeper question
                       |
                       v
                  Investigate
                       |
                       v
                  Re-evaluate
```

The Director should be able to recursively create sub-questions.

For example:

```text
Question:
Will NVIDIA sustain high growth?

        ↓

Finding:
Growth depends heavily on hyperscaler CapEx.

        ↓

New Research Question:
Can hyperscaler AI CapEx remain elevated?

        ↓

Finding:
Growth expectations depend on AI monetization.

        ↓

New Research Question:
Are hyperscalers generating sufficient economic returns
to sustain CapEx growth?
```

This recursive behavior is the key reason to use multiple agents rather than a single prompt.

---

# 9. Breadth vs. Depth

The system should explicitly optimize two dimensions.

## Breadth

Investigate multiple independent dimensions:

```text
Company
Industry
Competition
Customers
Suppliers
Financials
Macro
Technology
Regulation
Valuation
```

## Depth

When an important uncertainty is discovered, recursively investigate it.

Therefore:

> Multi-agent research is not simply parallel search.

The desired behavior is:

> **Parallel exploration + evidence evaluation + recursive investigation + adversarial validation.**

---

# 10. Workflow Artifacts

The implementation should keep the workflow definition lightweight.

The repository should contain something conceptually similar to:

```text
financial-research/
│
├── README.md
│
├── skills/
│   ├── research-planning.md
│   ├── fundamental-research.md
│   ├── industry-competitive-research.md
│   ├── financial-valuation.md
│   ├── evidence-analysis.md
│   └── bear-case.md
│
├── workflows/
│   └── deep-equity-research.md
│
├── orchestration/
│   └── director.md
│
├── examples/
│   └── nvidia-ai-infrastructure/
│
└── evaluation/
    └── research-quality.md
```

The Markdown files should describe:

* purpose;
* inputs;
* outputs;
* constraints;
* reasoning mandate;
* evidence requirements;
* handoff format;
* stopping conditions.

Do not try to encode every possible execution branch directly in Markdown.

The orchestration implementation should interpret these definitions and allow the Director to determine the actual execution path.

---

# 11. Minimal Implementation

Avoid building:

* a web application;
* a database;
* a full agent framework;
* a production API;
* authentication;
* a complex UI;
* a custom LLM infrastructure.

The prototype should be executable from a simple command or script.

The important artifact is the **research architecture**, not the software infrastructure.

Claude Code should be used primarily to:

1. create the Skill definitions;
2. implement minimal orchestration;
3. connect the available research tools;
4. execute the benchmark research question;
5. collect intermediate artifacts;
6. evaluate the final result.

---

# 12. Evaluation

The prototype should demonstrate that the architecture actually improves research quality.

Compare at least:

### Baseline

Single-agent research:

```text
Question
   ↓
LLM
   ↓
Report
```

### Proposed system

```text
Question
   ↓
Director
   ↓
Multiple Specialized Skills
   ↓
Evidence Analysis
   ↓
Recursive Research
   ↓
Bear Case
   ↓
Synthesis
```

Evaluate:

* research breadth;
* evidence coverage;
* source quality;
* factual consistency;
* numerical accuracy;
* citation quality;
* contradictory evidence discovered;
* depth of investigation;
* thesis robustness.

The purpose is not necessarily to prove that multi-agent is always better.

Instead, demonstrate:

> **For complex financial research questions, specialization and adaptive orchestration can produce a more structured and defensible research process than a single-pass LLM response.**

---

# 13. Demonstration Scenario

The primary demo should be a single difficult research question:

> **Is NVIDIA's current valuation justified by the expected growth of AI infrastructure spending over the next three years?**

The demonstration should show the actual execution trace.

For example:

```text
Research Director
  ↓
Created 8 research questions

Parallel Research
  ├── Fundamental Research
  ├── AI Infrastructure Industry
  ├── Hyperscaler CapEx
  ├── Competitive Landscape
  ├── Financial Analysis
  └── Valuation

Director Review
  ↓
Detected high uncertainty around
sustainability of AI CapEx

Deep Research
  ↓
Hyperscaler Economics
  ↓
AI Monetization
  ↓
CapEx Sustainability

Bear Case
  ↓
Competitive pressure
  ↓
CapEx normalization
  ↓
Margin compression
  ↓
Multiple contraction

Final Synthesis
  ↓
Investment Thesis
  ↓
Evidence Graph
  ↓
Bull / Base / Bear
  ↓
Monitoring Indicators
```

The execution trace is almost as important as the final report.

It allows an interviewer to see that the system is genuinely performing research rather than simply generating a polished answer.

---

# 14. What This Demonstrates in an Interview

The candidate should be able to explain the project through six capabilities.

### 1. AI Capability Design

"I don't treat an LLM as one giant assistant. I decompose financial research into reusable capabilities."

### 2. Agent Orchestration

"I use a Director to determine which capabilities are needed and how deeply to investigate them."

### 3. Financial Workflow Understanding

"The workflow is based on an actual equity research process rather than generic web search and summarization."

### 4. Ecosystem Thinking

"External data, research, tools and expert capabilities can be represented as Skills or Connectors and incorporated into the workflow."

### 5. AI Evaluation

"I evaluate claims, evidence, contradictions and research completeness rather than only evaluating whether the final prose looks good."

### 6. Product Thinking

"The final objective is not a chatbot answer. It is a reusable research workflow that can become a product capability."

---

# 15. What We Explicitly Do NOT Build

To keep the project focused:

* No full autonomous financial agent.
* No attempt to replace professional analysts.
* No trading recommendation engine.
* No production-grade financial data platform.
* No custom model training.
* No complex frontend.
* No large-scale infrastructure.
* No dozens of Skills.

The objective is to demonstrate **architecture, research methodology, AI workflow design and financial domain understanding**.

---

# 16. Success Criteria

The prototype is successful if an interviewer can look at it and conclude:

> "This candidate understands how AI capabilities can be decomposed, packaged as Skills, and orchestrated into a sophisticated financial workflow."

A strong demonstration should make the following visible:

```text
Financial Research Expertise
             +
Reusable AI Skills
             +
Dynamic Multi-Agent Orchestration
             +
Evidence-Based Research
             +
Adversarial Validation
             +
Adaptive Research Depth
             =
AI-Native Financial Research Workflow
```

The prototype should therefore be judged primarily on **the quality of the research architecture and the quality of the resulting research process**, not on the amount of code.
