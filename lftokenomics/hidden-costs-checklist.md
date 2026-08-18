# Where the hidden cost hides

The reusable checklist from Lesson 2. Run all five on every "should be pennies" estimate before
believing it.

## 1 · The real input, not the question alone

A user's question is rarely the whole input. Add the system prompt, any retrieved context (RAG), and
anything else the call sends every single time. For a grounded system, the retrieved context is
usually the largest single piece — often 10–50× the size of the question itself.

## 2 · Growing conversation history

Each turn in a multi-turn conversation re-sends the prior turns as context, unless the system is
specifically designed not to. A five-turn conversation doesn't cost 5× one turn — it costs
1+2+3+4+5 = 15× one turn's input, because turn five re-sends everything turns one through four
already sent.

## 3 · Output tokens, priced differently

Output tokens are usually priced higher than input tokens — often 3–5×. A system that produces long,
detailed answers costs meaningfully more per call than one designed to answer tersely, independent
of how many calls are made.

## 4 · Retries and failures

A call that times out, gets rate-limited, or returns something the system rejects and retries costs
money twice (or more) for one useful answer. Nobody's naive estimate budgets for this, and it's
rarely zero in production.

## 5 · Embedding and reranking calls

A RAG system doesn't just call the main model — it calls an embedding model to turn the query into a
vector, and sometimes a separate reranking model to re-order retrieved results. Each is a distinct,
separately billed call. Individually cheap, collectively a real and recurring line on the bill, and
the one most naive estimates never mention at all because it's invisible from the outside.

---

## The multiplier this usually adds up to

Not a small correction. In the case worked through this drill, real input (60× larger than assumed)
and real call volume (2.4× larger than assumed) compound to roughly **14×** the naive number. Numbers
this large are common enough that "check the real multiplier before quoting a number to a client" is
the single most useful habit this drill teaches.
