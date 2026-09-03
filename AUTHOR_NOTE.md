# Author Note — Replacing the Generated Solutions at Recording

> **Internal — do not ship to learners.** This note is for the author/recorder.

Every `example-output.md` and everything under `exercise/solution/` is an **AI-generated stand-in**. It was produced by actually running the author's prompts/assets (reasoning modules) or by computing on the real datasets (data modules) — not hand-waved — so a reviewer can see the intended shape and the folders aren't empty. **When you record, replace these with your actual on-screen outputs.** The `walkthrough.md` is your script/reasoning; the `example-output.md` is the artifact to end on.

## What to replace, by type

**Reasoning modules — SP1–SP6 and M6 (Claude Code, generative)**
Outputs are genuine Claude runs, but generative output **varies run to run**. When you demo live (or solve the exercise), capture your actual output and replace `example-output.md` if it differs materially. Content/structure will match; exact wording won't.

**Data modules — SP7, SP8, SP9 (computed — accurate)**
Outputs (CSVs, charts, numbers) are computed from the real provided datasets and are correct. **These belong to different modules and do not compose:** SP7's 30-day CPA mid averages **$49.84**; SP8 validates a *separately constructed* starter forecast averaging **$48.09** against actuals of $52.78, which is the **+9.75%** systematic bias. Feeding SP7's forecast into SP8 would give +5.9%, not +9.75%. CVR on-target. SP9: LTV $51.50 (discount) vs $315.90 (full-price) — **margin-adjusted at 65% gross margin**, per SP9's stated assumption / India-as-confound. Keep as-is, **or** re-run the analysis live and replace. If you ever regenerate the datasets, re-run the analysis so the numbers stay in sync.

**M8 (AI creative) — direction-only**
`example-output.md` has the real Claude direction + self-contained image prompt + copy, but **no images** (no image tool in the authoring environment). At recording, generate the actual images in your image tool and add them to the solution.

> **Alt text is required for every image you add here — five of them (three exercise variants, two demo).** This module is the only one that ships images as deliverables, and its method deliberately composites the headline, tagline and CTA onto the plate, so each finished image *contains text*. `Accessibility Standards.md` prohibits images of text because screen readers can't reach them and they blur when enlarged.
>
> Two things keep this compliant, and both need doing at record time:
> 1. **Write alt text per image** describing the scene, the composition, and the on-image copy verbatim. Don't write "ad creative for Vessl" — describe what a sighted learner sees and reads.
> 2. **Keep the copy present as text nearby.** It already is — headline, tagline and CTA appear in `creative-brief.md`, `brand-voice-guide.md`, and both solution files — so don't strip those when you replace the placeholders. That redundancy is what makes the images supplementary rather than the only carrier of the copy.
>
> The compositing method itself is fine: the prohibition targets images used to *present course information* (its examples are data tables and formulas), not depictions of the marketing artifact the module teaches you to make.

**M9 (background agent) — live web sources, time-sensitive**
*Exercise solution:* the brief + audit use **real web sources** captured at authoring time (competitor pricing; market-size estimates). Prices and market figures change — **re-verify every cited source at record time** and update. The teaching points should still hold (pricing is trustworthy and consistent; the market-size "CAGR" disagrees wildly across firms — 7.49%–19.5%; and the unnamed "market-research summaries" trend claim is a **Drop**, because no usable source can be identified even though the trend is probably real), but confirm the specific numbers and links.

*Demo:* runs a **different research question** from the exercise on purpose — which sustainability claims the category already makes, from `background-agent-research/demo/sustainability-claims-research-request.md` — so the demo doesn't pre-solve the exercise. Its `example-output.md` is **placeholders only**: `[Brand A]`, `[N]%`, `[YYYY-MM-DD]`, no URLs, nothing verified. Run the subagent live on camera, audit what it actually returns, and replace the file. Target verdict mix is 1 Trust / 2 Verify-first / 1 Drop, deliberately unlike the exercise's 2 / 1 / 2.

## Provenance at a glance

| Module | Output provenance | Action at recording |
|---|---|---|
| SP1–SP6, M6 | genuine Claude run (varies run to run) | re-run live; replace if materially different |
| SP7, SP8, SP9 | computed from real datasets (accurate) | keep, or re-run analysis |
| M8 | Claude direction only, **no images** | generate real images, add to solution |
| M9 | exercise: **live web sources** (time-sensitive); demo: **placeholders only** | re-verify sources + update numbers/links; capture the demo run live |

## Also worth knowing

- Exercise solutions are **one strong example** — student submissions will legitimately differ; grade against the requirements in the exercise `INSTRUCTIONS.md`, not against an exact match.
- **SP5 demo** now has a provided senior-dog persona panel (`synthetic-ab-test/demo/persona-panel-senior-dog.md`); the recorded run should score those three personas. The **SP4 demo** likewise has its senior-dog research asset (`synthetic-persona-interviews/demo/research-snippets-senior-dog.md`).
