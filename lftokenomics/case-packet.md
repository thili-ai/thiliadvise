# Case packet — pricing the catalog-and-voice system

_`scenario as of 2026-08-18`. Continues `lfdiagnose`'s case — same retailer, same RAG-for-catalog +
prompting-for-voice system, now being priced before launch._

## The ask

> "We expect about 50,000 customer questions a month once this launches. Our vendor quoted $0.002
> per 1,000 input tokens and $0.008 per 1,000 output tokens — should be pennies, right?"

## The naive math

50,000 questions × ~50 input tokens (just the question) + ~150 output tokens, at the quoted rates:

```
50,000 × (50/1000 × $0.002 + 150/1000 × $0.008) = 50,000 × $0.0013 = $65/month
```

Feels free. It's wrong.

## What it misses

A RAG call's real input isn't the question alone:

| Piece | Tokens |
|---|---|
| System prompt | ~500 |
| Retrieved catalog context (top-matched chunks) | ~2,000 |
| Growing conversation history (session average) | ~450 |
| The question itself | ~50 |
| **Real input per call** | **~3,000** |

Real call volume is higher too — a session averages 2.4 turns, and each turn is a separate call that
re-sends the growing history:

```
50,000 sessions × 2.4 average turns = ~120,000 real calls/month
```

Real output per call: ~200 tokens (a helpful, specific answer, not a one-word reply).

## The corrected math

```
120,000 × (3,000/1000 × $0.002 + 200/1000 × $0.008)
= 120,000 × ($0.006 + $0.0016)
= 120,000 × $0.0076
= $912/month
```

**≈14× the naive estimate.**

Plus a separate, easy-to-forget line: ~120,000 embedding calls for retrieval — cheap individually
(roughly $0.60/month total at typical embedding rates) but a real dependency and a real bill line,
not zero. Work through this with `hidden-costs-checklist.md` before filling in `COST_MODEL.csv`.
