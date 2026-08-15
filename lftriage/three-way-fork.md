# The three-way fork

The reusable checklist from Lesson 1. Not "is this hard" — the deciding question is what *kind* of
mapping the request actually needs. Ask these three, in order, and stop at the first yes.

## 1 · Is there a historical outcome with a ground-truth label, and will tomorrow's cases
statistically resemble yesterday's?

Yes → **classical ML**. You need examples of the thing actually happening in the past — not just
activity logs, an actual answer key (did they churn, was it fraud, did they default).

## 2 · Is the task open-ended and language-native — drafting, summarising, answering, explaining —
where "correct" has room to vary?

Yes → **GenAI**. The output is prose, and there is more than one acceptable way to write it.

## 3 · Could a person follow the whole thing as a numbered list of explicit rules, with no learning
or generation involved?

Yes → **plain software**. If you can write the rule on a whiteboard, you do not need a model to run
it — of either kind.

---

## The tell it's actually a fork, not a lane

Some requests answer "yes" to more than one question. That is not a sign you scoped it wrong — it is
a sign the request is **compound**: two or three jobs, stitched into one sentence, usually by
whoever wrote the request rather than whoever will build it.

**The trap:** a client who says "written by AI," "smart," or "automatic" is describing the *feeling*
they want, not the architecture. Their own phrasing will often nudge you toward using one tool —
usually a language model, because that is the AI everyone has personally used — for every part of
the request, including the parts it is worst suited for. See `case-packet.md` for a worked example.

## Why the order matters

Check for a ground-truth label first, not last. A request that *sounds* like it needs judgement or
language often turns out to have a clean historical answer key sitting in a database nobody thought
to look at — and a classical model beats a language model on exactly that kind of task. See
`hidden-cost-ml.md` and `hidden-cost-genai.md` for why.
