# Case packet — the InsightDesk demo

_`scenario as of 2026-08-15`. Made up for this drill; a composite, not a real vendor or client._

## The demo, as it happened

A retail client is evaluating **InsightDesk**, pitched as an AI system that triages incoming support
tickets and drafts replies. The vendor runs a live demo for the client's team.

| The client asks | The vendor's answer |
|---|---|
| (Demo opens) | Five pre-selected sample tickets are run, all answered fluently and correctly. |
| "How accurate is this?" | "94% accuracy in our benchmarks." No further detail offered. |
| "How fast is this at our volume?" | "It's very fast — sub-second." |
| "What happens with an angry or ambiguous ticket?" | The rep moves to the next slide. |
| "Where is our customer data processed?" | "Our infrastructure is enterprise-grade and secure." |

## The tell

Each vendor answer maps to exactly one of the five questions this drill teaches, evaded a different
way: no eval methodology, no off-happy-path proof, no real load number, no real answer on data
location. Lessons 2–4 work through why each answer is a non-answer, and what a genuine answer would
have looked like instead.

## Second case — the mixed-signal demo

A different vendor, evaluated for document processing, is **not** uniformly evasive:

- **Honest:** shares real benchmark methodology and the test set used.
- **Honest:** demonstrates live on a genuinely messy document the audience picks on the spot.
- **Partial:** asked about latency at volume, gives a real single-request latency number — but not a
  throughput or concurrency figure, so it doesn't actually answer what happens under real load.
- **Evasive:** answers a data-*residency* question with "we're SOC 2 compliant" — a real
  certification, but not an answer to *where* the data goes.
- **Evasive:** has no story for what happens when the system is wrong — no correction path, no audit
  trail.

This case is for Lessons 3–4: not every vendor scores 0/5 or 5/5, and the scorecard has to grade each
question on its own rather than average to one verdict.
