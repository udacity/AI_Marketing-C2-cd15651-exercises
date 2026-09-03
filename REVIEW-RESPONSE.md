# Review response — C2 (cd15651)

> **Temporary — remove by 2026-09-18.** Parked in this repo so the reviewer can read it alongside the code it describes. It is a *response to an external review*, not course material and not learner-facing. Delete once the reviewer has it.

**52 issues checked against the shipped files; all arithmetic recomputed independently.** Strong review — the ramp count, $51.11/$49.84, the five CPA line numbers, 64/45/29, 53/52/50, $670/$393/$377 and 21-of-30 all reproduced exactly.

**Status: all 52 addressed and pushed · 0 deferred · 0 open questions.**

🟢 **fixed** · 🔴 **disagreed, with reason**

---

## ai-generated-creative
🟢 **1** The gap was a missing **handoff**, not a missing tool. The module's design is deliberate — Claude Code for the prompt, then a separate image tool of the learner's choice, with the critique loop running *across* the two. That is the point of the demo's "context doesn't travel between tools." Both solution files now state the handoff explicitly: paste the self-contained prompt into your image tool, generate there, carry the context by hand. *(We briefly "fixed" this by pointing learners at inline generation in claude.ai — that inverts the module's whole lesson, and has been reverted.)*
🟢 **2** Real defect, now fixed: the file said images "are not included here (no image tool in this environment)" and then narrated a first generation coming back staged. The iteration note is now labelled **illustrative** — the critique the cross-tool loop produces — and both files agree on what the first pass got wrong (high-contrast, staged) and what fixed it (soft daylight, matte finish, candid, open negative space).
🟢 **3** Variants 2–3 were 9- and 14-word fragments — expanded to full standalone prompts in both files.
🔴 **4** Not a contradiction: the same prompt reserves *"open space top-left for text"* and the copy is composited after. Real gap was that nobody said so — **compositing note added**. *("Hydation" is a typo in the review; repo is clean.)*

## background-agent-research
🟢 **1** `Write` removed. Confirmed zero Write steps module-wide.
🟢 **2** Fixed with **5** — check 3 ("Current?") is now answerable from the new **Accessed** column.
🟢 **3** Brief narrowed to **3–5 brands** to match delivery.
🟢 **4** Mapping rule added (all four checks pass → Trust · mixed → Verify-first · two-plus fail or no identifiable source → Drop). **Kept your vocabulary** — Trust/Verify-first/Drop. "Partial" stays as a *Verified-against-source?* cell value, which is what it always was.
🟢 **5** **Access date, recorded inline per claim**, plus the source's own date where it shows one. Subagent definition updated to return both, so the column is fillable from its output.
🟢 **6** Scope aligned to "water bottle market" — it was the lone outlier and contradicted its own next line.
🟢 **7** Hydro Flask price now recited from **Hydro Flask's own product page**; the Yahoo listicle is gone. 🔴 Real brand names break no rule — `Real-World Content Guidelines.md:31` permits them for product comparison. And claim 4 was dropped for having **no** source, not for SEO.

## claude-code-knowledge-work
🟢 **1** Refinement step added to both solution files: a follow-up prompt that tightens the email's opening, with before/after — and the point that the draft never gets re-pasted, which is the persistent-context payoff.

## cpa-cvr-forecast
🟢 **1** Confirmed exactly, and the collision was real: SP8's sample forecast *was* SP7's ramp-excluded fit (slopes matched to six figures; CPA avg $49.84 to the cent). **Resolved by fixing both.** SP7 now excludes ramp *and* promo, as you asked. SP8 gets a **new** under-projected forecast built on a different error — fatigue assumed to plateau (+$0.11/day against an actual +$0.36/day) rather than a trend-window choice. The two modules now teach different failures.
🟢 **2** Updated with **1**: CPA **$46.6 / $49.8 / $53.1**, CPM **$13.9 / $14.3 / $14.7**. Your without-ramp CPM figures reproduce exactly. *(Mid was $15.01, not $15.02.)*
🟢 **3** Width is constant across all three metrics, confirmed. Kept ±1σ and **named it honestly** — one line stating it's a fixed-width uncertainty band, not a prediction interval, and to widen it manually if volatility compounds.

## evaluate-ai-tools
🟢 **1** Root cause was upstream of the solution: the framework defines **six** dimensions, the profiles supplied evidence for **five**, and the solution silently scored five. Added a brand-voice/brand-safety bullet to all four profiles — with real tension (Penmark locks voice tightest and checks claims not at all; CopyFlow drifts but ships the only banned-words filter; BrandForge alone has a compliance trail).
🟢 **2** Split, and it pays off: **CopyFlow tops the raw total (23) and comes last on the heavy three (8)**; Penmark is the mirror (21 / 14). Both totals now shown as separate rows — the gap between them is the lesson. The demo was on five dimensions too; aligned.
🟢 **3** → CopyFlow. *(Penmark 17 was tied-lowest with BrandForge, not sole lowest.)*
🟢 **4** Test brief and **two contrasting model outputs** added, so the baseline's capability 4 is evidenced rather than asserted — one output ships as-is, one breaks three named brief constraints.
🟢 **5** Step 3 had zero coverage in the solution *and* the demo. Added the two-way-door sizing beat, using the Durability lines that exist for exactly that purpose.
🔴 **6** Memo says "no **added** cost or data risk" — "added" is load-bearing and defensible against a 3/5 *absolute* score. 🟢 Residual fixed: the solution now actually **does** what the profile asks and checks the existing plan terms.

## goal-rich-briefing
🟢 **1** Confirmed 4/5, 3/5, 3/5 — added Context to briefs 2–3 and Success criteria to all three, copied verbatim from `walkthrough.md`. Also restored "paying" to brief 3's audience.
🟢 **2** Three fabrications cut: "plan is still saved", "takes about a minute", and a fourth you didn't catch — "most days this month". 🔴 "Than almost anyone" kept: it's puffery over a supported fact, a different class from an invented feature.
🟢 **3** → *Audience*. The quoted trigger is verbatim the Audience line.

## ltv-to-bidding — 🟢 dataset regenerated
Your diagnosis was right and understated. One root cause generated **1, 2, 3, 4, 8 and 9**: `revenue_to_date = monthly_fee × tenure` for **100% of 1,200 rows**, so no retention curve existed. June had 0 churn events — hazard 0, **LTV infinite**. `monthly_fee` was *perfectly* 1:1 with income band, so the confound you flagged in **4** couldn't be separated even in principle. And CPA was **inversely** rank-correlated with LTV, so the "where low CPA hides low LTV" deliverable was undemonstrable.

Patching the numbers wouldn't have fixed any of that, so the dataset was regenerated — and grown **1,200 → 4,800 rows**, because the old one couldn't support its own lesson: IN's full-price cell held **55 customers and 11 churn events**, making "geography flattens within acquisition type" swing 50% on noise. Any run that showed it flat was luck. It now holds ~233 and the claim is stable at a **7.0% spread**.

🟢 **1** Every cohort now carries **300+** churn events; no infinite LTV. **2** "Confidence" is now defined and, deliberately, *not* called a confidence interval — precision on a hazard is ≈ 1 ÷ √events, so each LTV is recomputed at hazard × (1 ± 2 ÷ √events) and shipped as `LTV_lo`/`LTV_hi` alongside the event count that drives the width. It prices sampling noise in the churn count and nothing else, so it is labelled **directional**. **3** Referral is now the cheapest traffic *and* the least valuable (~$11.12 CPA, ~$81 blended) because the referral offer **is** a discount — so 69% of its volume arrives discounted. High CPA on search is justified; cheap referral isn't a bargain. **4** Fee now overlaps all three income bands, so price and income are separable rather than assumed apart. **8** Tiering rule stated and defensible: LTV:CAC ≥ 6 high, 3–6 mid, < 3 low, against the standard 3× payback bar. **9** You were right that it was revenue:CAC. A **65% gross margin** is now stated — skipping it inflated every ratio ~1.5×.

**One thing your review didn't catch, and it's the better lesson.** The old cohort method made *younger* cohorts look more valuable — backwards from the censoring warning the module teaches. The cause isn't fixable by reseeding: pooling a two-hazard mixture (3%/mo and 18%/mo) tends to the **arithmetic** mean of hazards over a short observation window and the **harmonic** mean over a long one. So a blended cohort hazard *must* under-value young cohorts. §1 now teaches that as a three-step: revenue-to-date (r = −0.99 with cohort age) → blended hazard (r = −0.59, better but still biased) → hazard within acquisition type (r = **+0.11**, corrected). Same "don't average across a mix" lesson as the geography trap, one level up.

All ~140 published figures are verified against the shipped CSV in code.
**5, 6 and 7 were fixed against the old data first, then superseded by the regeneration.** All three outcomes hold, with new figures: **5** the income confound is now stated as discount accounting for **68% of low-band customers vs 26% of high-band** — and, more importantly, fee no longer determines band, so a learner can actually separate price from income instead of assuming. **6** the allocation note now names referral specifically and for the opposite reason — it is the *cheapest and least valuable* channel, which is the case your review asked the module to demonstrate and the old data couldn't. **7** the five negative acquisition costs are gone by construction; the generator floors cost at $1.10 and the shipped file has none.

*(For the record on issue 1: $78/$326 weren't reproducible against the old file; $63/$311 were exact. Both are moot now.)*

## scaled-audience-research
🟢 **1** Your issue had two halves and we initially fixed only one. The count came down to **24–30**, but your actual complaint — *"the starter only has the variant prompt and nothing to run or collect isolated contexts"* — went unaddressed. It is now: the starter ships a **collection template** (the row format the solution assumes, which previously existed only inside the answer key, so learners invented their own and could not reconcile against it) and an **aggregation prompt** for the barrier-by-archetype cross-tab. SP5 shipped one of these and SP6 shipped none. The exercise also now demands **evidence** of independence — the system-reported run count, not the model's own claim — plus a **roster-bias audit** and a **surface note**. 🔴 Still no runner script: at 24–30 the judgement about *whether to script it* is the thing the module grades, and supplying the script answers the question for the learner.
🟢 **2** Proven — the n=120 percentages were exact twelfths. Closed with **1**.
🟢 **3** Cross-tab built and the walkthrough points at it. It has since been rerun at **24 responses, four per archetype** — the old 12 gave several n=1 cells where a single answer read as a "segment pattern". Now 7 barrier categories × 6 archetypes, every column totalling 4. **Bonus:** building it exposed "strongest across every archetype" as false; durability appears in 4 of 6, absent among new-puppy and large-breed owners.
🟢 **4** → 6 archetypes, and the two missing ones added to the walkthrough's list.
🟢 **5** Codebook published, and it makes the call explicit: durability and chewing stay **separate** because they take different marketing responses — durability answers with materials and warranty, chewing with a chew-resistant SKU or an honest disclosure. Merging them yields one barrier at **9 of 24 (~38%)** that you can't act on with a single message. Demo taxonomy now agrees.

*Worth flagging on this module: at 24 responses there is **no dominant barrier** — the top category is one response in five and the six below it run 17% down to 8%. The roster-bias audit inverted with it. Durability is the only **response-decided** finding (3 of its 5 mentions come from archetypes not seeded for it); price is sharply **roster-decided** (8 of 24 personas seeded price-sensitive, and not one non-seeded persona raised it). That is a better result than the original — it shows the audit changing a conclusion rather than confirming one.*

## stress-test-strategy
🟢 **1** Confirmed — new signups never had sync, so the test measured nothing. Now a **grandfathered slice of existing free users**, the only group whose sync actually disappears. Revised position updated to match (it still said "new signups only").
🟢 **2** Both files now discount **critique 4**, quoted verbatim — and it's the lowest-ranked risk, so it no longer contradicts the ranking. *(Note: "en masse" **is** in the output — a misquote, not a fabrication. "Destroy the brand" was genuinely invented.)*
🟢 **3** You and my own earlier note were pulling opposite ways here (`skill_pair_feedback.md:43` asked for the list). Cut the enumerated list, kept the framing, renumbered the sections.

## synthetic-ab-test
🟢 **1** Confirmed inverted. Now stated from the actual numbers: **believability 4.67 strongest**, relevance and distinctiveness tied lowest at 3.67 — with the note that C still beats A and B on both.
🟢 **2** Per-dimension average table added to both files. It's where the *why* lives; totals alone hid it.
🟢 **3** → personas. The rule is one persona per conversation, all three directions within it.
🟢 **4** Count was **5**, not 3 — you missed the winner's own row (Priya/C `4/4/4/4`). **Rescored sum-preserving**: all nine totals unchanged, direction averages unchanged (12.7 / 11.3 / 16.0), margin still 3.3, panel split intact, flat cells **5 → 0**. Verified in code.

## synthetic-persona-interviews
🟢 **1** All three confabulation quotes inserted into the right persona's excerpt — 0 prior occurrences confirmed. Now matches the demo's provoke-then-annotate order.
🟢 **2** Q2, Q9 and Q10 now answered for **all three** personas, in character and grounded in each seed — without introducing new confabulations.
🟢 **3** → "behavioral prediction, never experienced". 🔴 Not a third marker — a mislabelled instance of marker 1; the demo already groups advocacy there.
🔴 **4** It **is** there — `walkthrough.md:15-17`, all three personas. 🟢 Absent only from `example-output.md`, which the build rule below now fixes.

## validate-forecast
🟢 **1** Confirmed unanswerable — notes column 100% empty, no promo week, no method note, training CSV not shipped. Clause dropped; diagnosis narrowed to what the shipped data supports.
🟢 **2** → "carried fatigue forward at the gentle training slope; actuals ran steeper". §4 already said this correctly, so §2 and §4 were contradicting each other.
🟢 **3** → **22 of 30 days** (21 against the old sample forecast; the count moved when that forecast was rebuilt under **cpa-cvr-forecast 1**). Directional-bias conclusion unaffected either way.

---

## The build rule your review produced

Your **P4**, **P2**, **K1** and **G2** were all one question: which file owns a deliverable. Settled as a standing rule:

> **`example-output.md` must independently satisfy every "What to produce" bullet.** `walkthrough.md` is the teaching narrative; `example-output.md` is what learners compare their own work against. A deliverable that lands in only one of them can't be self-checked.

Applied across all twelve modules this pass.

## A second pass, and what it found

Fixing 52 issues introduced 8 new defects. A regression review caught them and they are closed, but the pattern is worth stating plainly: **every one was invisible from inside the session that made the fix.** Examples — a cohort CSV left on the old confidence-interval formula while its three siblings were converted; summary prose contradicting a cross-tab that had just been regenerated correctly; a CFO-facing report that broke the "no model internals" rule it was written to satisfy; a demo whose "hypothetical" figures matched the solution's real channel costs to the cent.

Two things follow. Verification has to be mechanical rather than by eye — every number in the data modules is now recomputed from the shipped CSVs in code, not read. And a second reviewer has to be someone who did not make the fixes.

## Pattern worth flagging

**Exercise solutions kept carrying text that was true of the *demo*.** SP5's inverted dimension claim was correct for the demo's numbers · SP6's durability coding contradicted the demo's taxonomy · SP3's demo scored five dimensions against a six-dimension framework · SP4's confabulation quotes had regressed from the demo. Each is now aligned, and demo-vs-exercise diff is on the checklist for anything not yet reviewed.
