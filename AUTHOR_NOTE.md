# Author Note — Replacing the Generated Solutions at Recording

> **Internal — do not ship to learners.** This note is for the author/recorder.

Every `example-output.md` and everything under `exercise/solution/` is an **AI-generated stand-in**. It was produced by actually running the author's prompts/assets (reasoning modules) or by computing on the real datasets (data modules) — not hand-waved — so a reviewer can see the intended shape and the folders aren't empty. **When you record, replace these with your actual on-screen outputs.** The `walkthrough.md` is your script/reasoning; the `example-output.md` is the artifact to end on.

## What to replace, by type

**Reasoning modules — SP1–SP6 and M6 (Claude Code, generative)**
Outputs are genuine Claude runs, but generative output **varies run to run**. When you demo live (or solve the exercise), capture your actual output and replace `example-output.md` if it differs materially. Content/structure will match; exact wording won't.

**Data modules — SP7, SP8, SP9 (computed — accurate)**
Outputs (CSVs, charts, numbers) are computed from the real provided datasets and are correct: CPA ≈ $51 / +5.9% systematic bias / CVR on-target / LTV $96 (discount) vs $447 (full-price) / India-as-confound. Keep as-is, **or** re-run the analysis live and replace. If you ever regenerate the datasets, re-run the analysis so the numbers stay in sync.

**M8 (AI creative) — direction-only**
`example-output.md` has the real Claude direction + self-contained image prompt + copy, but **no images** (no image tool in the authoring environment). At recording, generate the actual images in your image tool and add them to the solution.

**M9 (background agent) — live web sources, time-sensitive**
The brief + audit use **real web sources** captured at authoring time (competitor pricing; market-size estimates). Prices and market figures change — **re-verify every cited source at record time** and update. The teaching point should still hold (pricing is trustworthy and consistent; the market-size "CAGR" disagrees wildly across firms — 6.75%–19.5%), but confirm the specific numbers and links.

## Provenance at a glance

| Module | Output provenance | Action at recording |
|---|---|---|
| SP1–SP6, M6 | genuine Claude run (varies run to run) | re-run live; replace if materially different |
| SP7, SP8, SP9 | computed from real datasets (accurate) | keep, or re-run analysis |
| M8 | Claude direction only, **no images** | generate real images, add to solution |
| M9 | **live web sources** (time-sensitive) | re-verify sources + update numbers/links |

## Also worth knowing

- Exercise solutions are **one strong example** — student submissions will legitimately differ; grade against the requirements in the exercise `INSTRUCTIONS.md`, not against an exact match.
- **SP5 demo** now has a provided senior-dog persona panel (`synthetic-ab-test/demo/persona-panel-senior-dog.md`); the recorded run should score those three personas. The **SP4 demo** likewise has its senior-dog research asset (`synthetic-persona-interviews/demo/research-snippets-senior-dog.md`).
