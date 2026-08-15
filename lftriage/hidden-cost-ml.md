# Classical ML's hidden cost

The commitment checklist from Lesson 2. If the fork points at classical ML, this is what the client
actually just signed up for — not "a model."

## 1 · Labelled training data

**"We have data" is not "we have labels."** Usage logs, tickets, and transactions are not the same
as a ground-truth answer key — for a churn model that means a historical record of who *actually*
cancelled, not just who was active. If nobody can point at the column that says "did this happen,"
there is no classical-ML project yet, only a data-collection one.

## 2 · A training loop

Someone owns re-running it, evaluating it against held-out data, and versioning what changed between
runs. Training a model once is a demo. Owning the loop that produces the next one is the job.

## 3 · A retraining cadence

Customer behaviour drifts — a pricing change, a new competitor, a seasonal shift — and a model
trained on last year's world quietly gets worse at describing this year's. Nobody decided *when* it
retrains is itself a decision, and usually the wrong one.

## 4 · Drift monitoring

Is the world the model sees today still the world it was trained on? That's a question that needs
instrumentation — comparing today's inputs to training-time inputs — not a gut feeling from whoever
built it.

## 5 · A serving layer

Something has to actually run the model against new data, reliably, on a schedule or on demand. That
is engineering work distinct from the model itself, and it's where most of the ongoing cost actually
lives. If your client's engineer is building and hosting this, `lfserving` on Learn Fast is the drill
that covers this checklist in full engineering depth.

---

**Going stale, silently:** a classical model does not throw an error when the world has moved on. It
keeps producing confident scores — just against an outdated picture of reality. Nobody notices until
the wrong customers get the discount, or the right ones churn anyway, weeks or months after the drift
started.

This is not a reason to avoid classical ML — it is often the cheapest, most defensible option,
especially at scale (see `hidden-cost-genai.md` for the comparison). It is the list a client is
agreeing to when they say yes.
