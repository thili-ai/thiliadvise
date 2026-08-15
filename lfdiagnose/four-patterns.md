# The four honest patterns

These four patterns are the standard vocabulary for what an AI system can honestly do. Most vague AI
asks decompose into exactly one of these. When a request won't decompose cleanly, that's the tell
it's two projects wearing one sentence — see `case-packet.md`.

| Pattern | What it means | Example |
|---|---|---|
| **Extract / classify** | Pull structured information out of unstructured input, or sort it into categories | Route a support ticket, flag a contract clause, tag a lead |
| **Draft / summarise** | Produce a first-pass document a human edits | Draft a reply, summarise a call, write a first product description |
| **Search your own data** | Answer questions grounded in a specific, changing corpus | "What does our refund policy say", "what's in stock" |
| **Take action** | The system does something, not just says something | Issue a refund, update a record, send an email |

The catalog-and-voice case is **search your own data** (the catalog) plus a **constraint on every
pattern's output** (the voice) — not a fifth pattern. Voice is never the main pattern; it's always a
layer on top of one.
