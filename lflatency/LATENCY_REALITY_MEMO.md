# Latency reality memo — [vendor / system name]

_Written: [date]_

---

## 1 · The claim as first given

[The vendor's or client's original latency number, verbatim, and what it was measured against —
if that's even known.]

---

## 2 · What that number is actually describing

[Time-to-first-token, a single-call latency, an unloaded-system measurement — name which one, and
why it isn't the same as "how fast does a real user's request complete."]

---

## 3 · The corrected chain

| Hop | Time |
|---|---|
| | |

**Total, realistic:** [ ]

---

## 4 · The three questions to put back to the vendor

1. **What's the p50 and p99 latency, not an average?** [ ]
2. **Is this time-to-first-token or total response time?** [ ]
3. **Under what concurrent load was this measured?** [ ]

---

## 5 · Where this routes next

| If this is unresolved | Next step |
|---|---|
| Real load figures still missing | Ask for a load test before signing, not a demo |
| Latency is a hard product requirement | Revisit the technique call in **Build vs. Buy vs. Prompt** — a shorter answer or fewer chain hops may matter more than a faster model |

---

_No submission, no grading. The proof this memo worked is that the vendor's next answer has real
numbers attached to it, not a single figure._
