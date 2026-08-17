# Data readiness checklist — [client / dataset name]

_Written: [date]_

---

## The six items

| # | Item | Finding | Tag |
|---|---|---|---|
| 1 | Volume | | [ ] Blocking · [ ] Fixable · [ ] Approach-changing |
| 2 | Label quality | | [ ] Blocking · [ ] Fixable · [ ] Approach-changing |
| 3 | PII exposure | | [ ] Blocking · [ ] Fixable · [ ] Approach-changing |
| 4 | Consent / licensing | | [ ] Blocking · [ ] Fixable · [ ] Approach-changing |
| 5 | Staleness | | [ ] Blocking · [ ] Fixable · [ ] Approach-changing |
| 6 | Access control | | [ ] Blocking · [ ] Fixable · [ ] Approach-changing |

---

## For each "fixable" item: the estimate

[Named amount of work — hours, days, a specific person's time — not "some cleanup needed."]

---

## For each "approach-changing" item: what changes

[Not just "this is a problem" — what it changes about the recommendation. E.g. inconsistent labels
might mean a smaller, human-reviewed gold set instead of the full raw export.]

---

## Overall verdict

- [ ] Proceed — the data supports the project as scoped
- [ ] Proceed after fixes — name them and the timeline
- [ ] Do not proceed on this data — name what would need to change

---

## Where this routes next

| If this is the finding | Next step |
|---|---|
| Data supports the approach | Back to **Build vs. Buy vs. Prompt** to confirm the technique |
| Real cost of fixes is unclear | **Token Economics & Cost Modeling** |
| PII/consent scope is genuinely unresolved | Flag as a legal question, not a technical one — do not proceed on judgement alone |

---

_No submission, no grading. The proof this memo worked is that the client knows exactly what stands
between them and a usable dataset — not just that "more work is needed."_
