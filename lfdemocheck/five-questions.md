# The five questions a demo is scripted to evade

The reusable checklist from Lesson 2. Ask all five, every time — a vendor's charm or the client's
excitement is not a reason to skip one.

## 1 · What eval methodology was run?

"94% accuracy" is not an answer on its own. Accuracy on what test set? Scored by whom? What was
excluded from the test set — the hard cases, the ambiguous ones? A real answer names the dataset, the
scoring method, and who ran it. A non-answer repeats the number louder.

## 2 · What happens off the happy path?

Every demo runs the cases that work. The question is what happens on a case that doesn't — an
adversarial input, an ambiguous request, a case the system should refuse. A real answer shows this
live, on a case the client picks, not the vendor. A non-answer changes the subject.

## 3 · What's the latency and throughput under real production load?

Five sequential demo calls tell you nothing about concurrent load at the client's actual volume. A
real answer gives p50/p99 latency and a throughput number under realistic concurrency. A non-answer
says "fast" or "sub-second" with no load behind it.

## 4 · What data leaves the client's systems, and where does it go?

A real answer names the region, the subprocessors, and the retention policy. A non-answer says
"secure" or "enterprise-grade" — words that describe a feeling, not a location. A compliance
certification (SOC 2, ISO 27001) is real and worth having, but it answers "is there a process," not
"where does the data go" — don't let one substitute for the other.

## 5 · What happens when it's wrong?

A real answer names a correction path, an audit trail, and where a human reviews or overrides a bad
output. A non-answer has nothing here at all — which is itself the answer, just not the one that got
said out loud.

---

## Scoring a vendor's answer

Not every evasion looks the same. When scoring, mark each question one of:

- **Answered** — specific, checkable, given without being asked twice.
- **Partially answered** — real information, but not the actual question (a certification instead of
  a location; an average instead of a p99).
- **Evaded** — changed the subject, repeated a marketing line, or simply wasn't addressed.

A vendor scoring three "answered" and two "evaded" is a different, more nuanced situation than one
scoring zero — see `case-packet.md`'s second case.
