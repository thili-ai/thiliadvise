# thiliadvise

The blank templates for **AI Judgment for Consultants & Client-Facing Teams** — the `lfaiconsultant`
track on [Learn Fast](https://learnfast.thili.ai). One folder per drill: the case packet you work
through, the reusable checklists the drill teaches, and the blank memo you fill in and hand to a
client.

There is no code here. These are plain text files — a case to read and a memo to write.

> ⚠️ **Templates, not answers.** Every memo below is deliberately empty. The value is the judgement
> call you make and write down against a real client situation — a filled-in memo copied from
> someone else's client is worth nothing.

## If you have never used GitHub

You do not need an account and you do not need to understand this site.

1. Click the green **`< > Code`** button near the top of this page.
2. Click **Download ZIP**.
3. Unzip it somewhere you will find again — your Documents folder is fine.

That is it. Open the files in any text editor, or in Notes, Word, or Google Docs — they are just
text. The `.md` ending means "plain text with simple formatting"; nothing needs installing to read
it.

## One folder per drill

Each drill in the track gets its own folder here, added as the drill is authored — this repo grows
with the track rather than being built all at once.

| Folder | Drill | Status |
|---|---|---|
| [`lftriage/`](./lftriage/) | **ML, GenAI, or Just Software?** — does this need a model at all, and if so, which kind? | authored |
| [`lfdiagnose/`](./lfdiagnose/) | **Build vs. Buy vs. Prompt** — given it's GenAI, prompt, RAG, or fine-tune? | authored |
| [`lfdemocheck/`](./lfdemocheck/) | **Reading a Vendor Demo** — what is this demo not showing me? | authored |
| `lfdataready/` | The Data Readiness Audit | planned |
| `lftokenomics/` | Token Economics & Cost Modeling | planned |
| `lflatency/` | The Latency Reality Check | planned |
| `lfguardrails/` | Hallucination & Guardrails | planned |
| `lfinjection/` | Prompt Injection & Data Leakage | planned |
| `lfblastradius/` | Agent Blast Radius | planned |
| `lfisitworking/` | Is It Actually Working? | planned |
| `lfpilotdeath/` | Why Pilots Die | planned |

## What's inside each drill's folder

The shape repeats across drills: a **case packet** (the client scenario the lessons walk through),
one or two **reusable checklists** (the frameworks that outlive the specific case), and one **blank
memo template** — the graded deliverable, named for what it produces.

`lftriage/`, for example:

| File | Lesson | What you do with it |
|---|---|---|
| `case-packet.md` | 1–4 | The client scenario every lesson works from — read, don't edit |
| `three-way-fork.md` | 1 | The three questions that sort a request into ML / GenAI / plain software |
| `hidden-cost-ml.md` | 2 | What a classical-ML project commits a client to |
| `hidden-cost-genai.md` | 3 | What a GenAI project commits a client to |
| `TRIAGE_MEMO.md` | 5 | **The deliverable.** Fill this in for the case packet, or for a real request once you've taken the drill |

## Why case packets are made up

Every case packet in this repo is a composite, not a real named client or vendor incident — see each
drill's `case-packet.md` for its `scenario as of <date>` line. Where a real, citable public example
exists, it's linked from that drill's page on Learn Fast, not folded into the packet itself. This
keeps the judgement teachable without misrepresenting a fictional scenario as someone's real
engagement.

## Where this comes from

**AI Judgment for Consultants & Client-Facing Teams** is a track inside the Learn Fast `lffounder`
group — the non-technical side of the catalog. It shares that group with the founder/operator track
(`lffounder-lfstack` and others): same format, same "no code, one memo per drill" shape, different
reader. This track is for the person advising *someone else's* company on an AI decision, not running
their own.

## License

MIT © thili.ai — use these on your own client work, change them, share them.
