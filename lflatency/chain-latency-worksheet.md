# Why an agent chain is slow

The reusable worksheet from Lesson 3.

## The default is sequential

Unless someone deliberately engineers otherwise, each hop in a multi-call chain waits for the
previous hop to finish before it starts. Total chain latency is the **sum** of every hop's latency,
not the slowest one and not an average.

```
Total ≈ hop 1 + hop 2 + hop 3 + ... + hop N
```

## Applying it to the running case

| Hop | Time |
|---|---|
| Embed the question | ~80ms |
| Vector search | ~40ms |
| Rerank | ~150ms |
| Model prefill | ~200ms |
| Model decode (~200 tokens) | ~5,000ms |
| **Total** | **~5,470ms** |

Four of the five hops together add under 500ms. Decode alone is more than ten times that — in most
RAG or agent chains, the generation step dominates total latency, not the retrieval steps that
usually get the most engineering attention.

## What actually shortens a chain

- **Parallelize what doesn't depend on prior output.** If reranking doesn't need the embedding
  step's exact output structure, it may be possible to overlap steps — real engineering work, not a
  given.
- **Cut hops.** Every hop removed is pure latency saved, unlike optimizing a hop's internal speed.
- **Shorten the answer.** Decode time is the largest single lever in most chains, and it's controlled
  by how long the model is asked to write, not by infrastructure.

## The question this earns you the right to ask

"Is this latency number for one call, in isolation, or for the full chain a real user actually
waits through?" Most vendor-quoted numbers describe the former.
