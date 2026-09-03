# Change Note — Learner Dry-Run Round

> **Temporary — remove by 2026-09-18.** Working record for the author/reviewer, not a learner-facing file.
>
> **Status: audited twice.** A peer session and an independent auditor both checked this note against the repo. Both found errors *in the note* and in the fixes it describes; all are corrected below, and the sections headed *"Breaks introduced"* and *"Changes the first draft failed to describe"* exist because of them. Where a claim here was retracted, it says so rather than being quietly deleted.

## What a dry-run is

An agent attempts an exercise using **only** `exercise/starter/` — no answer key — produces the deliverables for real, and only then opens `exercise/solution/` to compare. It catches a class of defect that proofreading cannot: things the answer key silently assumes but the starter never states.

All twelve modules were run, in five batches: SP9 · SP7+SP8 · SP1+SP2+SP3 · SP4+SP5+SP6 · M6+M8+M9.

**Eighteen changes across ten modules**, plus one made and then reverted, listed below. **SP2, SP4 and SP8 came back clean** and needed no changes. SP8 notably so — every reasonable bias rule agrees and no verdict flips. That accounts for all twelve: ten changed below, two clean (SP8 gained a tolerance band as prevention, not as a defect fix).

---

## Changes applied

### SP9 — `ltv-to-bidding`

**1. Forecast horizon was undefined, making the answer unscoreable.**
Max observed tenure in the dataset is 10 months. Plain Kaplan-Meier truncates there and yields full-price LTV ≈ **$83** (tier: mid). The key's pooled hazard extrapolates a constant hazard to infinity and yields **$316** (tier: high) — its own solution concedes 73% of that sits beyond the last data point. The starter said "account for that censoring," which is the standard cue for Kaplan-Meier. So a learner doing textbook survival analysis *correctly* missed the key by 4×.
→ Starter now requires the learner to name their horizon and say roughly how much LTV sits past the last data point.

**2. "Confidence" was required but never defined.**
The key uses `hazard × (1 ± 2/√events)`; nobody lands on that independently.
→ Formula now stated in the starter, with the explicit caveat that it is a directional spread, not a statistical confidence interval.

**3. The horizon choice changed the graded tier.**
SP9's fix (item 1) requires learners to name their horizon, but naming it doesn't settle which answer scores: truncating gives ~$83 → **mid**, extrapolating gives $315.88 → **high**, and the bidding-signal deliverable requires a tier.
→ SP9's key now states both tiers are acceptable when the horizon is named, and that an unstated horizon is not — grade the statement and the rule, not the tier.

---

### SP7 — `cpa-cvr-forecast`

**4. The answer key contradicted its own demo.**
The demo tells learners CPA *"can't be extrapolated as a single line — forecasting it means understanding its drivers."* The key then fits a single linear trend directly to CPA. Computed on identical clean days:

| Method | CPA mid | vs actual $52.78 |
|---|---|---|
| Key — linear on CPA | $49.84 | −5.6% |
| What the demo prescribes — forecast CPM/CTR/CVR, derive CPA | **$54.30** | **+2.9%** |

The decomposed method is *more* accurate, yet $54.30 sat above the key's own high case of $53.10 — so following the demo read as out of range.
→ Key now names both methods as acceptable, states the decomposed route lands near $54, and sets **$46–$55** as the acceptable band for a defensible CPA mid. Grade the stated method and reasoning, not the number.

**5. "Three distinct patterns" where four are defensible.**
CPM and CTR drift are separately significant with different causes, so a learner naming four is right and would think they miscounted. **Magnitudes, on the basis the exercise actually uses** — a linear fit over the 69 promo- and ramp-excluded days, fitted endpoints: CPM **+15.5%**, CTR **−28.1%** (p = 2.4e-18, 8.9e-26). *An earlier draft also quoted full-span figures of +17.6% / −32.0%. Those do not reproduce — recomputing the full 90 days gives +24.8% / −29.1% at p = 3.2e-27 / 2.0e-27, and a p-value is fixed by the regression, so no way of expressing the change accounts for the gap. They have been removed rather than corrected.*
→ Three references changed from a fixed count to "the patterns you found," with an explicit invitation to defend a fourth.

### SP6 — `scaled-audience-research`

**6. Time budget was wrong by 3×.**
Budgeted at 30 min; the dry-run put it at 90–120 min for 24–30 persona variants plus a findings report. **That is an agent's estimate of human effort, not a stopwatch figure** — treat 90 as the best available number, not a measurement.
→ `exercise_demo_planning.md` updated to **90 min**.
⚠️ This now makes SP6 by far the longest exercise in the course (next is SP5 at 40 min). Flagged for the author — it may indicate the exercise is over-scoped rather than under-budgeted.

**7. The shared stimulus could be contaminated — and the note first misdiagnosed this.**
*Filed by the dry-run as "the starter never states the stimulus." That was wrong: the barrier question and product blurb are both in the starter at `INSTRUCTIONS.md:3`.* The real, narrower defect is that the starter never gave the barrier question **verbatim**, and "furniture-grade" invites a premium-price inference. The dry-run agent added "premium priced" to the stimulus every persona heard — seeding price into all 24 variants at once, rather than only the two archetypes deliberately built price-sensitive. Price then tops the rankings and the leave-one-out finding inverts: price reads response-decided, durability thin — the reverse of the key.
→ Starter now gives the question verbatim — *"What would stop you from buying this furniture-grade modern dog bed?"* — and states that price sensitivity belongs in archetype attributes, never in the shared stimulus.
**The key's conclusion did not need to change, and `REVIEW-ROUND2.md`'s closure of the roster-bias defect stands.** It was always reachable; the starter just didn't protect the path to it.

**18. The graded independence evidence could not be obtained.**
The requirement was *"the run count your tool reports."* No Claude surface reports that — `/cost` returns tokens and duration; the dry-run only recovered it by grepping session JSONL with `jq`. And if "Work in Claude" is read as claude.ai, subagents aren't user-accessible at all.
→ Replaced with evidence that lives in the output rather than the tool: line up all 24 opening sentences and read down the column. Cross-references, a shared vocabulary settling in for the same objection, or near-duplicate phrasing all mean context leaked. Propagated to the walkthrough, Common Mistakes, and the worked example's independence check.

### SP8 — `validate-forecast`

**19. No numeric tolerance, unlike SP7 and SP9.**
SP8 came back clean from the dry-run, so this is prevention rather than a defect: CPA bias computed as mean-over-mean gives +9.8%, but the mean of daily percentage errors gives a slightly different figure and both are defensible.
→ Key now states **+8% to +12%** acceptable for CPA and **±1%** for CVR, and that the graded object is the verdict those numbers support, not the second decimal.

### SP5 — `synthetic-ab-test`

**8. A one-run artifact was graded as a required finding.**
Common Mistakes penalised "missing that A is a polarizing targeted play." The dry-run's panel had C winning unanimously and A uniformly mediocre — so a learner correctly reporting *no split* was marked wrong.
→ The graded miss is now **not looking for a split**, not failing to find one. "Your run may show no split at all; reporting that honestly is correct."
(The starter-side half of this was already fixed: the aggregation prompt now says a split can hide at any rank, not only the winner.)

### SP3 — `evaluate-ai-tools`

**9. The Cost dimension was unscoreable.**
CopyFlow's pricing is tiered — $18/seat, 150 pieces included, $0.20/piece overage, free tier capped at 20/mo — but no starter file stated how much copy Cobbleway actually writes.
→ Starter now states **~45 pieces/month**. Chosen to sit above the 20/mo free cap and below the 150 included, so the tier structure becomes meaningful, and to differ from the demo's 20 so it doesn't pre-solve.

**10. The key cited a fact that existed nowhere.**
The key's reasoning referenced "our existing terms — business tier"; no starter file contained the company's AI plan terms.
→ Terms added to the starter.

### SP1 — `goal-rich-briefing`

**11. The instructions steered into the wrong answer.**
Guidance warned against over-prescription while itself prescribing "replace them with a clear goal" — but the key's answer for that prompt is **Audience**, one of only three graded dimensions.
→ The prescription removed.

### M8 — `ai-generated-creative`

**12. REVERTED — the compositing step was added to the starter, then withdrawn.**
The dry-run found that the starter mandates the tagline *"Hydration, handled."* and never mentions a layout tool, so a learner reading cold could bake the tagline into the image prompt and get garbled type. A requirement was added telling learners to end prompts *"no text in image"* and composite the copy afterwards.
→ **Reverted on author instruction (2026-09-04).** The starter is back to its pre-round state. Note that *"no text in image"* still appears in the solution's and demo's example prompts — that predates this round (commit `d944d5a`) and was not touched.
⚠️ The underlying gap is therefore **still open**: nothing a learner reads before attempting says the copy is composited rather than generated. Whether that matters depends on how the module is recorded — if the demo shows the compositing step on screen, the starter may not need to.

### M6 — `claude-code-knowledge-work`

**13. A required deliverable had no file.**
The one-line persistence note was required in both What-to-produce and Done-when but never assigned a home.
→ Goes at the end of the consistency-check file. (An earlier draft of this note said `consistency-check.md`; M6 deliberately prescribes no deliverable filenames, and the edit doesn't either.)

**14. The key's findings were run-specific but presented as the answer.**
Its two drifts arise from the specific refinement *it* performs; a careful learner produces different drift. Unlike M9's key, M6's never said results would differ.
→ Added M9's inoculation: "yours will be different drifts, and that is the expected result."

### M9 — `background-agent-research`

**15. The environment requirement was stated nowhere.**
Both halves need live web access — the agent researches, the learner opens sources to audit. Also, `.claude/agents/` is not picked up if created inside an already-running session.
→ Both stated up front, plus a note that per-site permission prompts are normal rather than a fault.

**16. The delegation brief was required in What-to-produce but absent from Done-when.**
→ Added.

**17. The key's "Drop" verdicts assumed unsourced claims.**
The shipped subagent definition instructs it to source every claim, so a well-behaved run yields no Drop — and the learner never practises the checklist's most interesting verdict.
→ The checklist now states that a claim can carry a working link and still Drop: a source that publishes a figure without disclosing method, or that is flatly contradicted by a source of equal standing, has failed two checks.

---

## Not fixed — decisions still open

**SP6 — the 90-minute change is not propagated.** `exercise_demo_planning.md:256` is correct, but **eight** derived artifacts still say 30 min: `generated/combined/` — `combined_scripts_part1.md`, `combined_scripts_part3.md`, `C2_video_roster_TABLE.html`, `C2_video_handoff_ALL.html`, and the three `gdoc/` renders (`combined_scripts.html`, `_part1.html`, `_part3.html`) — plus `project/shot_list_roster.json`. `source/module_dictionary.csv` still budgets module 6 at 45 min against a planning doc now needing 100. And `exercise_demo_planning.md:232` still justifies the Claude Code choice with *"can't be done by hand across 100+ chat conversations"* — stale against the 24–30 in the same file. These are regenerated artifacts; the fix is a rebuild, not hand-editing. **Author decision (2026-09-04): leave as-is.** The 90 min stands in the planning doc; the derived artifacts will pick it up at the next rebuild. Anyone reading the roster or handoff docs before then will see 30 min.

**M9 — the new Drop rule is asserted but never demonstrated.** Both Drops in the worked solution are still "no source to open" cases, and `walkthrough.md:40` still frames a Drop that way, so the link-works-but-fails-two-checks verdict has no worked example. **Author decision (2026-09-04): leave as-is** — the rule stands in the checklist without an example. (A real one is available if wanted: a smart-water-bottle market sized at $292M by one firm and $2.8B by another for the same year, both with working links, neither disclosing method.)

*The second half of this — the authoring-source copy at `exercises-and-demos/assets/templates/source-quality-audit-checklist.md` missing the paragraph — is now **fixed**. The paragraph was propagated and the two files differ only in their line-3 header, which is deliberate.*

> ⚠️ **Do not reconcile these two files by making them identical.** Their line-3 headers differ *deliberately*: the exercises-repo copy names the exercise, while the authoring template was genericized to *"for auditing an agent-returned research brief"* precisely so a reusable template can't carry a stale exercise title — that was the original defect it was fixed for. Propagate the Drop paragraph; leave the header divergence alone. The same caution applies to SP3's assets.

**M6 — the fresh-session requirement is unenforceable.** The evidence lives in `~/.claude/projects/*.jsonl`, outside the learner's workspace. A grader cannot distinguish a genuine restart from `/clear` or from one long session; the artifacts are identical. Making it checkable would mean asking learners to submit a session ID. **Author decision (2026-09-04): not doing that.** The requirement stays honour-system. The starter's own self-check — *"If you have to re-paste anything, your working context was never on disk"* — is the lever, and the learner who skips the restart mainly cheats themselves out of the lesson.

---

## Changes the first draft of this note failed to describe

An independent audit found the round is **larger than the first draft's 15 items**. Now folded in above as items 3 and 7, plus these:

- `evaluate-ai-tools/exercise/starter/ai-tool-evaluation-framework.md` (`01e6bca`) gained a whole paragraph: *"The weighted score narrows the field; it does not make the call... If your recommendation simply reads off the highest score, you have skipped the judgement this framework exists to support."*
- `ltv-to-bidding/exercise/solution/walkthrough.md` gained the solution-side half of SP9's horizon fix (item 3). The note originally described item 1 as starter-only.
- In the parent repo, the same hunk that set SP6 to 90 min also changed variants from **"100+" to "24–30"** in three places (`exercise_demo_planning.md:257, 261, 268`), rewrote SP5's key takeaway, and touched `asset_inventory.md:18`.

## Breaks introduced by these fixes, then repaired

Three of the changes above broke something on their way in. All three are now fixed; recording them because they show the failure mode.

**SP7's pattern-count fix was half-applied.** Three references were changed; a fourth — bolded and imperative, in the authoritative Requirements section — still read *"Find all three."* The starter contradicted itself in the same file. The solution's *"Three patterns to separate:"* was also untouched. Both now fixed.

**SP7's widened band contradicted its own budget read-out.** The key blessed $54 as a defensible mid and, three lines later, used *"past $54"* as the point where orders fall below the downside case: $30,000 ÷ $54.30 = **552 orders**, under the stated downside of 565. The read-out now carries the decomposed figure explicitly and says to report off whichever mid you forecast; the risk line no longer hard-codes $54.

**SP3's volume fix broke the key's cost arithmetic.** The added sentence *"Two of those three people write"* implied **2 seats**, while `tool-profiles.md:17` prices a seat per person generating copy. Both keys state *"Three seats, which is the team we have"* with CopyFlow $54 / Penmark $360 / no-training tier $447 — every per-seat figure became 1.5× what the starter supported. Reworded to *"All three generate copy, none of them full time,"* restoring derivability. (The ranking never flipped, so no recommendation changed.)

---

## Verification status

Every change above is a text edit to instructions or answer keys. **No datasets, computed figures, or charts were regenerated in this round**, so the prior round's numeric verification still holds. To be precise about what that verification was: the round-2 pass *did* find real failures — k=1.96 bands in `ltv-by-cohort.csv`, the CFO report's −8.88% written as "10%", SP9's demo "±4%" against a 9.56% rule. The "138 checks, zero failures" figure describes the **re-run after those were fixed** (2026-09-04), not a claim that no numeric defects ever existed.

### What is and isn't evidenced

Recomputed from the shipped data **in this session**, not taken from any agent's report:

| Claim | Verified value |
|---|---|
| SP9 confidence formula reproduces the solution CSVs | **23 of 23** lo/hi pairs |
| SP9 Kaplan-Meier truncated (E[months] 8.45, max tenure 10) | ~$82.4 |
| SP9 constant-hazard (hazard 0.030939, life 32.3 mo, mean fee $15.04) | $315.9 |
| SP7 key's linear-on-CPA 30-day mid | $49.8445 |
| SP7 decomposed 30-day mid | $54.2974 |
| SP7 holdout actual (n=30) | $52.7843 |
| CPM / CTR significance, 69 clean days | p = 2.4e-18 / 8.9e-26 |

*The p-value row previously read `3.9e-33 / 3.7e-61 (90-day span)`. Those were the fabricated figures retracted above — they had survived here, in the one table that claims recomputation, after being withdrawn from the body. Replaced with the clean-day values, which are the basis this note argues is the relevant one.*

Asserted but **not** corroborable from the repo: SP6's 90–120 min figure, the SP5 dry-run's panel result, and the round-2 "138 checks" tally. Treat these as agent-reported.

### How much to trust this record

This note was produced by one session, then checked by a second session and an independent auditor. Across that exchange, on twelve markdown-and-CSV exercises, **thirteen errors were caught between two careful sessions**: 8 defects introduced by round-1 fixes, 5 verification errors on the reviewing side (three pattern-matching false positives, one claim gone stale across a dataset rebuild, one revenue-vs-margin confusion that nearly wrote bad figures to a CSV), 2 fabricated numeric claims from the auditor, and 3 things these dry-run fixes broke on their way in.

**Every one was caught by the other party recomputing from source. Not one was caught by re-reading the same evidence.** Both sides re-read their own work repeatedly and found nothing.

Two consequences for anyone using this document:
1. Re-reading it will not find its remaining errors. Recomputing from `exercise/starter/` will.
2. The auditor that found the SP7 read-out contradiction — a real defect neither session would have caught alone — also fabricated two numeric claims. Treat structural findings from agents as leads worth checking; treat any number they produce as unverified until recomputed.

**Nothing here has been attempted by a human learner.** These findings come from AI dry-runs, which surface real gaps but overstate blockers that are artifacts of the agent's own environment — M8 was reported as "blocks outright" solely because the agent had no image tool, which is not a defect for a learner who does.
