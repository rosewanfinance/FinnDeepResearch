# Example: AMD / AI Accelerator Market

Second benchmark demonstration for the multi-agent financial research workflow. Its focus is
**competitive share capture** (vs. the NVIDIA example's focus on TAM growth). The question lives in
[`question.md`](question.md).

## Artifacts a complete run produces

A full run (executed by the Research Director per
[`orchestration/director.md`](../../orchestration/director.md)) should write these into `output/`:

```text
output/
├── plan.md              # the sub_questions research plan
├── trace.md             # execution trace: spawns, deep-dives, stops, decisions
├── findings/            # one structured finding per sub-question (from each subagent)
│   ├── fundamentals.md
│   ├── industry.md
│   ├── competitive.md
│   ├── hyperscaler-silicon.md
│   ├── valuation.md
│   └── ...
├── evidence-audit.md    # the evidence-analysis output (claims, flags, contradictions)
├── bear-case.md         # the devil's-advocate challenge block
└── memo.md              # the 12-section final research package
```

The `trace.md` is as important as `memo.md` — it is the artifact that shows the system genuinely
researched (planned, delegated, deepened, challenged) rather than generated a polished answer.

## Expected trace shape

```text
Research Director
  ↓
Created N research questions
  ↓
Parallel research (fundamentals, AI accelerator TAM, competitive vs NVIDIA, hyperscaler silicon, valuation)
  ↓
Evidence evaluation → detected high uncertainty around converting design wins into revenue share
  ↓
Deep research (CUDA moat economics → ROCm software ecosystem → Instinct ramp)
  ↓
Bear case (CUDA lock-in, custom-silicon squeeze, margin compression, multiple contraction)
  ↓
Final synthesis → memo + evidence graph + bull/base/bear + monitoring indicators
```

## Notes

- This directory is a template; `output/` is generated at run time and is not part of the
  definition files.
- The key differentiator to watch in a run: whether the Director *deepens* into the CUDA-moat /
  software-ecosystem question (the highest-importance, lowest-confidence uncertainty) rather than
  accepting a surface answer about "AMD winning share."
- For the interview narrative, the six capabilities from the proposal (§14) map onto the artifacts:
  plan (`plan.md`), delegation (`trace.md`), evidence discipline (`evidence-audit.md`), adversarial
  validation (`bear-case.md`), and the final package (`memo.md`).
