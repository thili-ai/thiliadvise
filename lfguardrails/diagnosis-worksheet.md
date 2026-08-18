# Diagnosis worksheet — why did it confidently make something up?

A hallucination needs two ingredients missing. Work through both before reaching for a fix.

## 1 · Was the actual answer present in context?

- [ ] **Not present at all** — nothing relevant was retrieved or included. The model has nothing to
      ground an answer in and generates from pretraining instead.
- [ ] **Present, but stale or wrong** — a real, relevant source was retrieved and cited accurately,
      but the source itself is out of date or incorrect.
- [ ] **Present, but incomplete** — a real, relevant source was retrieved, and it's correct as far as
      it goes, but it doesn't cover the specific detail the answer states.

## 2 · Was the model under any pressure to say "I don't know"?

- [ ] **No** — the system prompt and pipeline give the model no signal that abstaining is an
      acceptable, expected response to a gap.
- [ ] **Yes, but weak** — an instruction exists ("if you're not sure, say so") but nothing enforces
      it structurally; the model can and does ignore it under normal fluency pressure.
- [ ] **Yes, and enforced** — a measured confidence or retrieval-relevance score gates whether the
      model is even allowed to generate a confident answer.

## 3 · Name the root cause in one sentence

_Combine 1 and 2. Example: "No grounding (nothing relevant retrieved) and no abstention pressure
(nothing told the model to stop) — the default failure mode for an untouched system."_

> [ ]

## 4 · What this rules out

A fix aimed at the wrong ingredient does nothing. If grounding was actually present and correct
(the "stale source" case), no amount of abstention tuning or constrained output fixes it — the fix
is a data-freshness process, not a generation-time guardrail at all. Name what this diagnosis rules
out before moving to `mitigation-ladder-checklist.md`:

> [ ]
