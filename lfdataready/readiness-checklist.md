# The six-item data readiness checklist

The reusable checklist from Lesson 2. Run all six on every dataset a client offers, before any model
work starts.

## 1 · Volume

"We have data" is not "we have enough of the *right* data." Row count misleads — after removing
boilerplate, duplicates, and templated content, real information content is usually a fraction of
the raw count. Rare but high-value categories are often the thinnest slice of all.

## 2 · Label quality

A label that looks like ground truth (e.g. "resolved") can hide massive inconsistency in how
different people applied it. A model trained on inconsistent labels learns the inconsistency, not
the intended concept.

## 3 · PII exposure

What counts as PII, and how it hides, changes by data type — see `data-types-matrix.md`. The
consistent rule: **consent to collect is not consent to train.** A recording taken "for quality
assurance" was very likely scoped to internal coaching, not to training a model whose outputs may be
served by a third-party vendor.

## 4 · Consent / licensing

Check the actual scope of the original consent or licence, not just whether one exists. Training a
model — especially one where data leaves the company via a third-party API — is very often outside
the scope a privacy policy or content licence was written for.

## 5 · Staleness

Data that was accurate when collected can be actively wrong by the time it's used — a policy that's
changed, a price that's moved, a product that's been discontinued. Nothing in the data itself flags
this; a model trained on it will state the old fact with the same confidence as a current one.

## 6 · Access control

Before calling an export "clean," check what fields it actually contains. Internal notes, escalation
comments, and partial payment details routinely survive into exports someone assumed were
customer-facing only.

---

## Tagging a finding

Every item gets tagged one of three ways in the memo:

- **Blocking** — the project cannot proceed until this is resolved.
- **Fixable** — resolvable with a named amount of work (say how much).
- **Approach-changing** — resolving it changes which technique or scope makes sense, not just the
  timeline.
