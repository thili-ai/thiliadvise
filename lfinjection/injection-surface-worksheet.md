# Injection surface worksheet

## 1 · Classify the attack

- [ ] **Direct** — the attacker is the user, typing the injection straight into the system.
- [ ] **Indirect** — the attacker plants the injection inside a document the system will later
      retrieve on someone else's behalf. The victim is whoever's unrelated question triggers the
      retrieval, not the attacker.

## 2 · Name the attacker-controlled source

_Every source your system retrieves from or calls out to is a potential injection vector if anyone
outside your own team can write to it. List every one._

| Source | Who can write to it? | Attacker-reachable? |
|---|---|---|
| | | |

## 3 · Where would the hidden instruction actually enter context?

_Trace forward from the source you named: does it get indexed as-is? Is there a sanitization step?
Does retrieval treat it identically to fully trusted content?_

> [ ]

## 4 · What would the model do with it, and why

_Nothing in a model's context is structurally marked "trusted" vs. "retrieved" by default. State
plainly whether your system has any mechanism that makes that distinction — and if not, say so._

> [ ]
