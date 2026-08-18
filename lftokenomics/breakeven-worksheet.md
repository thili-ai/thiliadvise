# API vs. self-hosted — the breakeven math

The reusable worksheet from Lesson 3.

## The shape of the trade

| | API | Self-hosted |
|---|---|---|
| **Cost to start** | Near zero — call an endpoint | High — infrastructure, setup, ongoing DevOps |
| **Cost per call** | Fixed rate per token, scales linearly with volume | Effectively zero marginal cost once running |
| **Cost at low volume** | Low | High relative to what's being used |
| **Cost at high volume** | Rises without bound | Flat — the same fixed cost whether lightly or heavily used |

This is the same crossing-curves idea from **ML, GenAI, or Just Software?**, one level deeper: two
different cost shapes, and the volume at which one overtakes the other is a real, calculable number
— not a guess.

## Where the fixed cost actually comes from

"$1,500/month" isn't arbitrary — it's roughly what renting a single mid-tier GPU, always-on, costs
from a real provider (AWS, GCP, or a regional specialist like E2E Networks, which often undercuts the
two hyperscalers on GPU price specifically). Figures move constantly and vary by region and
commitment level — verify against a current rate card before quoting a number to a client.

## An API isn't just the model

A hosted API is rarely raw next-token generation with a price tag — it's a harness wrapped around the
model: content-safety filtering, structured-output enforcement, tool-calling orchestration, automatic
retries and fallback routing, rate limiting, observability. Self-hosting replaces the model. It does
not automatically replace the harness — that has to be built too, or the self-hosted system is
quietly less capable than the API it replaced.

## The calculation, done twice

**Pass 1 — infra only.** API cost at current volume ÷ ... no: solve `fixed cost ÷ cost per call` for
the crossing volume, using only the GPU rental as the fixed cost. This number is almost always too
low, because it prices a bare GPU, not a working replacement for the API.

**Pass 2 — infra plus a person.** Add a realistic fraction of an ML/DevOps engineer's fully-loaded
monthly cost — the time spent matching the API's harness, keeping the server patched and monitored,
and redeploying newer models. Even ~20% of one person's time meaningfully raises the fixed cost, and
therefore the crossing volume. Recompute the crossing point with this true fixed cost, and compare
*that* number to the client's actual growth trajectory — not the infra-only number.

## Serving speed and the other engineering challenges

Beyond the harness and the person, running a self-hosted model well is its own discipline:

- **Batching for throughput** — an API absorbs concurrent traffic elastically; a self-hosted server
  has to be deliberately engineered to batch requests, or it wastes GPU capacity.
- **No built-in autoscaling** — a spike an API absorbs invisibly can queue or fail on a server sized
  for average load.
- **Cold starts** — scaling down to save cost means real delay bringing the server back up.
- **Keeping pace with model updates** — an API's model quietly improves over time; a self-hosted one
  only improves when someone deliberately redeploys.

This is exactly what **Serve an LLM at Scale** teaches in engineering depth — the KV cache,
continuous batching, the scheduler. Naming that this work is real and needs a specific person's time
is enough for a readiness memo; building it well is a separate, deeper skill.

A recommendation to self-host based on the infra-only crossing point, without recomputing it with a
real person's time included, is not just incomplete — it can point at the wrong answer entirely.
