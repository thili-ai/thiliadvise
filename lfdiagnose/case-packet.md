# Case packet — the catalog-and-voice ask

_`scenario as of 2026-08-15`. Made up for this drill; the judgement it teaches does not expire, only
the sample scenario's date does. This is a composite, not a real client._

## The ask, verbatim

A mid-size retailer's brief, exactly as a client would actually send it:

> "We want a chatbot on our site that knows our whole product catalog and can answer questions about
> anything we sell. It should also sound like us — our brand voice is casual and a little funny, and
> we don't want it to sound like a corporate robot. Can you build this with fine-tuning on our
> product data and our old marketing copy?"

## The tell

This is **two** problems the client has bundled into one ask, and one proposed technique
(fine-tuning) that fits neither well:

- Catalog knowledge changes weekly — that's a retrieval problem.
- Brand voice is stable — that's a prompting / few-shot problem.

Neither needs the training data the client is offering to hand over. Run it through
`four-patterns.md` and `decision-tree.md` before filling in `BUILD_BUY_PROMPT_MEMO.md`.
