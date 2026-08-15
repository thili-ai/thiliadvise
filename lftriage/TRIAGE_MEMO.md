# Triage memo — [client / request name]

_Written: [date]_

One request, decomposed into what it actually is — before any vendor conversation, cost model, or
build call is possible.

---

## 1 · The request, as first stated

> [paste the ask verbatim, unedited — keeps the decomposition honest and checkable]

---

## 2 · Decomposition into parts

One row per distinct job. If there's only one, say so — not every request is compound.

| # | Part of the request |
|---|---|
| 1 | |
| 2 | |
| 3 | |

---

## 3 · Each part tagged, with reasoning

Run each part through `three-way-fork.md`.

| Part | Tag (ML / GenAI / software) | One-line reasoning |
|---|---|---|
| | | |
| | | |

---

## 4 · Hosting commitment each ML or GenAI part creates

One line each, from `hidden-cost-ml.md` / `hidden-cost-genai.md`. Skip this row for any plain-software
part — there isn't one.

| Part | Hosting commitment |
|---|---|
| | |

---

## 5 · The single biggest risk of picking the wrong bucket

[One sentence. What breaks, specifically, if this part is built with the wrong kind of system —
not "it might not work," but the concrete failure: cost, calibration, auditability, staleness.]

---

## 6 · Where each part routes next

| Part tagged | Next step |
|---|---|
| GenAI | `lfdiagnose` — prompt, RAG, or fine-tune |
| Classical ML, hosting unscoped | Their engineer takes `lfserving` |
| GenAI, hosting unscoped | Their engineer takes `lfllmserving` |
| Needs real cost numbers | `lftokenomics` |

---

_No submission, no grading. The proof this memo worked is that it correctly separated the request
before anyone started building the wrong part first._
