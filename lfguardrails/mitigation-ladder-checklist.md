# Mitigation ladder checklist

Five rungs, each stopping a different gap. Pick the rung(s) matched to your diagnosis and the actual
stakes — not the maximum by default, not the minimum.

| # | Rung | What it actually stops | What it doesn't |
|---|---|---|---|
| 1 | **Grounding / RAG** — index the real source, retrieve it | Answers with no source behind them at all | A wrong answer from a source that's present but outdated or over-extrapolated |
| 2 | **Citations** — require the model to name its source | Nothing on its own — makes verification *possible*, not automatic | Any failure, unless the citation is actually checked against the claim |
| 3 | **Constrained output** — a schema that can only be filled from what's literally in context | The model filling a real gap in a real source with an invented specific | A case where nothing relevant was retrieved at all — there's no source to extract from |
| 4 | **Confidence thresholds + abstention** — decline to answer below a relevance/confidence bar | A genuinely ungrounded question, caught before a fabricated answer is generated | A confidently-wrong answer from a source that scores as highly relevant because it genuinely is, just stale |
| 5 | **Human review gate** — route to a person before the answer is delivered or treated as binding | The cases nothing upstream catches, including stale-but-relevant sources | Doesn't scale for free — every gated answer costs a person's time |

## Sizing to stakes

| Stakes | What a wrong answer costs | Typical rung(s) |
|---|---|---|
| Low | Minor inconvenience, self-correcting (customer notices immediately) | Data freshness only — the rest is over-engineering |
| Medium–high | Real money, a commitment the business didn't intend to make, recoverable | Grounding + abstention threshold as a safety net |
| High | Physical safety, legal, or medical consequence | Full ladder plus a standing category rule — mandatory human/professional escalation, independent of the model's own confidence |

## Before finalizing

- [ ] Named which specific rung(s) address the diagnosed root cause — not a generic "add guardrails"
- [ ] Confirmed each chosen mitigation would demonstrably stop a specific wrong answer, not just
      describe what it's supposed to do (see: reduce vs. hide)
- [ ] Checked the stakes tier against the rungs chosen — neither over- nor under-applied
