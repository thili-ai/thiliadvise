# Risk ladder checklist

Four rungs, ordered by one question: if this action is wrong, can it be undone, and by whom? Not how
likely it is to be wrong.

| Rung | Test | Gate needed? |
|---|---|---|
| **Read-only** | Does anything in the world change state as a result of this action? | No |
| **Draft-for-review** | Does a person actively have to approve before anything real happens? | Already built in |
| **Auto-execute-reversible** | If wrong, can it be undone with no lasting cost? | Generally no |
| **Auto-execute-irreversible** | If wrong, is there no path back to the prior state? | Yes, always |

## Placing an action

For each action from `answer-vs-act-worksheet.md`:

1. **Does it change state at all?** No → read-only. Yes → continue.
2. **Does a human have to approve before it executes?** Yes → draft-for-review. No → continue.
3. **If it's wrong, can it be fully undone with no lasting cost?** Check both:
   - [ ] Is an undo mechanism technically available?
   - [ ] Will anything actually trigger someone to use it, or does it rely on someone happening to
         notice?
   - Both yes → reversible. Either no → **treat as irreversible**, regardless of what the undo
     button says is technically possible.

## The trap to check explicitly

- [ ] Have you priced any gate by *total exposure* (per customer, per day, per session) rather than
      by the size of any single request? A threshold on one request's size can be satisfied by
      splitting a larger request into several smaller ones — see the threshold-gaming case.

## Before finalizing

- [ ] Every action from the worksheet has a tier, not just the ones that sounded risky at a glance
- [ ] Every irreversible action has a named gate, or an explicit statement that none exists
- [ ] Checked whether "it worked in testing" is being used to justify removing a gate — it shouldn't
      be, on its own
