# Case packet — the same system, now questioned on speed

_`scenario as of 2026-08-18`. Continues the `lfdiagnose`/`lftokenomics` case — same retailer, same
RAG-for-catalog + prompting-for-voice support system._

## The ask

> "The vendor promised sub-200ms responses. That's basically instant, right?"

## The real chain, in order

| Step | What happens | Time |
|---|---|---|
| 1. Embed the question | Turn the customer's question into a search vector | ~80ms |
| 2. Vector search the catalog | Find the top matching product/policy chunks | ~40ms |
| 3. Rerank the top matches | Re-order retrieved results by relevance | ~150ms |
| 4. Prefill | The model reads the ~3,000-token input (system prompt + retrieved context + question) | ~200ms |
| 5. Decode | The model generates ~200 output tokens, one at a time, ~25ms each | ~5,000ms |
| **Total** | | **~5,470ms** |

## The gap

The vendor's "sub-200ms" almost certainly describes step 4 alone — time to first token, on an
unloaded system, for a short prompt. It does not describe the time to a complete, useful answer, and
it says nothing about what happens once real concurrent traffic arrives. Work through this with
`prefill-decode-worksheet.md` and `chain-latency-worksheet.md` before filling in
`LATENCY_REALITY_MEMO.md`.
