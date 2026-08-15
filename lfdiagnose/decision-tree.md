# The prompt / RAG / fine-tune decision tree

## 1 · Does the answer depend on facts that change, or are specific to this client?

Yes → needs **retrieval (RAG)** or a live data connection. A fine-tuned model's knowledge is frozen
at training time; a catalog is not.

## 2 · Is the issue how it says things, not what it knows?

Yes → **prompting / few-shot examples**. Style and format are cheap to steer with instructions; they
rarely justify a training run.

## 3 · Does the needed knowledge fit in a reasonable context window and can it be fetched at query
time?

If yes, **RAG beats fine-tune** on cost and staleness — no retrain cycle every time the underlying
data changes.

## 4 · Fine-tune only when:

The behaviour must be baked in regardless of prompt (a specific output shape at high volume where
prompt overhead costs real money), or the task requires a "shape" of response the base model won't
reliably produce even with good examples.

---

**The correction this tree makes almost every time:** most "let's fine-tune on our data" requests
are actually RAG-plus-prompting problems. True fine-tune need is real but rarer than client instinct
suggests — the tree exists to catch the reflex, not to rule fine-tuning out.

## Next drill by pattern called

| Pattern called | Next drill |
|---|---|
| Search your own data (RAG) | A retrieval-focused drill (not yet in the catalog) |
| A first working service, prompt-only | **Build Your First AI Service** |
| Take action (agentic) | see **Agent Blast Radius** first, then the relevant agents drill |
| Genuine fine-tune need | the fine-tuning track |
