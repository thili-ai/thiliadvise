# Case packet — the same retailer, now questioned on trust

_`scenario as of 2026-08-18`. Continues the `lfdiagnose`/`lftokenomics`/`lflatency` case — same
retailer, same RAG-for-catalog + prompting-for-voice support bot._

## The transcript

> Customer: "I bought this 45 days ago — can I still return it?"
> Bot: "Yes, our return policy allows returns within 60 days, no questions asked."

## What's actually true

The store's real return policy is 30 days standard, 14 days for electronics, receipt required, no
returns on opened consumables. None of that resembles what the bot said.

## Why it happened

This bot's retrieval corpus was built for the original catalog use case — product descriptions,
stock, prices. Nobody ever indexed the store's actual return-policy documents. When a policy
question arrives, retrieval returns nothing genuinely relevant, and nothing in the system tells the
model to stop there. It falls back on its pretraining and produces a fluent, wrong, confident-sounding
number.

## Work through it

1. `diagnosis-worksheet.md` — name the root cause: missing grounding, missing abstention pressure,
   or both.
2. `mitigation-ladder-checklist.md` — pick the rung(s) sized to what this specific wrong answer
   actually costs.
3. `GUARDRAIL_MEMO.md` — the finished deliverable.
