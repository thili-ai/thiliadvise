# Case packet — the call-and-chat export

_`scenario as of 2026-08-16`. Made up for this drill; a composite, not a real client._

## The ask

A subscription business wants to fine-tune a customer-support model on **two years of call
recordings and chat transcripts**, "so it sounds like our best agents." They hand over an export:
audio files for calls, text logs for chats, minimal structure, no documented consent scope, internal
agent notes still attached to the "customer-facing" transcripts.

Chosen to cover two data types — audio and text — in enough depth for a full six-item audit. Lesson 3
extends the same checklist to images, video, and time-series with shorter, separate examples.

## What the audit finds

| # | Item | Finding |
|---|---|---|
| 1 | Volume | 2M chat messages → ~40,000 unique after removing boilerplate and templated replies. The high-value category (escalations) is under 200 examples. |
| 2 | Label quality | "Resolved" was marked inconsistently — some agents close on an explicit thank-you, others close the moment the customer stops replying. |
| 3 | PII exposure | Names, account numbers, and partial card numbers appear inline in chat text; callers state PII out loud on calls; recordings also capture other household members' voices. |
| 4 | Consent / licensing | Recordings were collected under a policy permitting "quality assurance" review — not the same scope as training a model whose outputs may be served via a third-party API. |
| 5 | Staleness | Transcripts from 18 months ago describe a return policy that has since changed twice. Nothing in the data flags this. |
| 6 | Access control | The "clean" export still contains internal agent notes with card last-fours and named escalation comments — nobody checked which fields were actually included. |

Work through this with `readiness-checklist.md` before filling in `DATA_READINESS_CHECKLIST.md`.
