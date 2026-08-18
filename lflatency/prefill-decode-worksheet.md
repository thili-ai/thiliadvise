# Prefill vs. decode, in plain terms

The reusable worksheet from Lesson 1.

## The two phases

- **Prefill** — the model reads the entire input at once. This step parallelizes well and is
  comparatively fast, even for a large input — it's mostly one pass of computation.
- **Decode** — the model generates the output one token at a time. Each new token depends on every
  token before it, so this step is inherently sequential — it cannot be parallelized away. Generating
  200 tokens means running the model roughly 200 times, in order.

## Why this matters for a latency promise

A single "response time" number conflates two very different things. Time-to-first-token is mostly
prefill — fast, and roughly constant regardless of how long the answer will be. Total response time
is prefill plus the full decode — and decode time scales directly with how many tokens the answer
contains. A vendor's "sub-200ms" is a plausible claim about the first number and an implausible one
about the second, for any answer longer than a few words.

## The arithmetic

```
Total response time ≈ prefill time + (tokens in the answer × time per token)
```

At ~25ms per output token, a 200-token answer's decode alone takes ~5,000ms — before prefill, before
any retrieval steps, before network overhead. Ask which number a claimed latency figure is actually
describing before treating it as the answer to "how fast is this."
