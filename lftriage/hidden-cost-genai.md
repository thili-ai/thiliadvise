# GenAI's hidden cost

The commitment checklist from Lesson 3. If the fork points at GenAI, this is what the client
actually just signed up for. There's no training step, so it feels free to start. It is not free to
run — the cost just moves somewhere else.

## 1 · Per-call inference cost that scales with volume

Every request costs money, at every volume, forever. There is no upfront-then-cheap curve the way
there is with a trained model — the meter runs on every single call, from the first customer to the
millionth.

## 2 · Latency and throughput trade off against each other

An LLM answer is many small sequential steps, not one. Streaming makes an answer *feel* faster by
showing tokens as they arrive — it does not reduce total cost or increase throughput. Batching
increases throughput — it does not reduce latency for any one request. You cannot have both for
free.

## 3 · Prompt and context drift

A prompt that worked well in the demo can quietly degrade — as the underlying model version updates,
or as real users' phrasing diverges from the handful of test cases someone tried. There is no
"retrain" step that automatically fixes it; someone has to notice and rewrite the prompt.

## 4 · No natural refresh cycle

Unlike classical ML, there is no periodic retraining that re-grounds behaviour against new reality. A
GenAI system just keeps calling the same — or a silently updated — model, indefinitely, until someone
actively intervenes.

---

## The crossing curves

|  | Classical ML | GenAI |
|---|---|---|
| **Cost to start** | High — labelling and training before anything works | Low — call an API and get an answer today |
| **Cost to run at volume** | Low, once built and hosted | Rises with usage, indefinitely |
| **What breaks it** | Drift, if it is not retrained | The bill, if usage grows past what anyone modelled |

Draw those two as lines against volume and they cross. Below the crossing point — a prototype, a
low-volume feature, something needed *this week* — GenAI is cheaper and faster to ship. Above it,
classical ML usually wins on unit economics. That's exactly why a bank's fraud-detection system is a
classical model scoring millions of transactions a day, not an LLM call per transaction, even though
an LLM could technically do the classification.

**Token Economics & Cost Modeling**, later in this track, puts real numbers on exactly this crossing
point for a specific client's volume. If your client's engineer is building and hosting the GenAI
side, **Serve an LLM at Scale** on Learn Fast covers the KV cache, continuous batching, and token
economics in full engineering depth.
