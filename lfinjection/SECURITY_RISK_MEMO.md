# Security risk memo — [system / feature name]

_Written: [date]_

---

## 1 · The traced attack path

[Hop by hop, from the attacker-controlled source (or the non-malicious trigger, if there's no
attacker) through to the customer-facing outcome. Don't skip to the final answer — name every step.]

| Step | What happens |
|---|---|
| 1 | |
| 2 | |
| 3 | |

---

## 2 · Where it actually broke

[The earliest point in the chain where something could have stopped this — not just where it became
visible.]

---

## 3 · Mitigations mapped to break points

[For each mitigation, name the specific step in the traced path it would have broken the chain at.
"We have output filtering" is not an answer on its own — "output filtering catches this at step N,
after steps 1 through N-1 failed to" is.]

| Mitigation | Breaks the chain at step | Why |
|---|---|---|
| | | |

---

## 4 · Residual risk, stated honestly

["Reduced to X, not eliminated." Name what's still not covered.]

---

## 5 · Where this routes next

| If | Next step |
|---|---|
| | |

---

_No submission, no grading. The proof this memo worked is that the next version of this system's
attack surface is smaller than this one's — not that it's zero._
