# Solution — Forecast LTV, Compare Cohorts, Build the Value Signal

*Worked solution. LTV modelled from `steep_cohorts.csv` (4,800 customers, six monthly cohorts) with a churn-hazard method. Artifacts: [`ltv-by-cohort.csv`](ltv-by-cohort.csv), [`ltv-by-acqtype.csv`](ltv-by-acqtype.csv), [`ltv-by-channel.csv`](ltv-by-channel.csv), [`ltv-by-geo.csv`](ltv-by-geo.csv), [`bidding-signal-upload.csv`](bidding-signal-upload.csv), [`ltv-driver-chart.png`](ltv-driver-chart.png), and the allocation note [`allocation-note.md`](allocation-note.md).*

## Method (stated assumptions)

**51% of the base is still active**, so revenue-to-date is a floor, not a lifetime. Don't average it. Instead:

- **Monthly churn hazard** = churned ÷ total observed customer-months (per segment).
- **Expected lifetime** = 1 ÷ hazard (geometric).
- **Predicted LTV** = **gross margin** × average monthly fee × expected lifetime.

Two assumptions to state out loud, because the numbers move if you disagree:

- **Gross margin = 65%.** Steep ships tea, so a subscription dollar is not a margin dollar. Skip this and you are computing *revenue*-to-CAC and labelling it LTV:CAC, which flatters every ratio by ~1.5×.
- **No discount rate.** Lifetimes here top out near 32 months; discounting to present value moves the numbers a few percent and changes no ranking. Add it if you extend the horizon.

**Every LTV below ships with a range, and the range is driven by one thing: how many churn events sit behind it.** A hazard counted from 1,834 churn events is a firmer number than one counted from 48. The rule, in one line: **relative precision on a hazard ≈ 1 ÷ √events, so recompute LTV at hazard × (1 ± 2 ÷ √events)** — few events, wide range. Every `_lo` / `_hi` column in the artifacts is that.

Call it **directional**, not a confidence interval. It prices sampling noise in the churn count and nothing else — not the constant-hazard choice, not the margin assumption, and not the extrapolation flagged in §7.

## 1. LTV per cohort — and why the obvious version is still wrong

[`ltv-by-cohort.csv`](ltv-by-cohort.csv). Three columns, three different answers to the same question:

| Cohort | n | Months obs. | Avg revenue-to-date | Blended LTV | LTV range | full_price LTV |
|---|---|---|---|---|---|---|
| 2025-01 | 800 | 10 | $103.98 | ~$122 | $111 – $134 | ~$339 |
| 2025-02 | 800 | 9 | $94.61 | ~$111 | $101 – $122 | ~$296 |
| 2025-03 | 800 | 8 | $83.86 | ~$98 | $89 – $108 | ~$300 |
| 2025-04 | 800 | 7 | $79.87 | ~$117 | $106 – $131 | ~$323 |
| 2025-05 | 800 | 6 | $68.67 | ~$98 | $89 – $109 | ~$308 |
| 2025-06 | 800 | 5 | $61.85 | ~$104 | $93 – $117 | ~$335 |

**Read the three columns as a sequence of fixes.**

**Revenue-to-date (worst).** Falls from $104 to $62, almost perfectly with cohort age (r = **+1.00** against months observed). That is not six cohorts of differing quality — it is the same customers observed for ten months versus five. Rank cohorts on this and you will defund your newest acquisition for the crime of being new.

**Blended hazard (better, still biased).** Modelling churn removes most of it, but a tilt survives — older cohorts still read higher (r = **+0.59** against months observed). This one is subtle and worth understanding: your cohort is a *mixture* of a ~3%/mo segment and an ~18%/mo segment. Pool them into one hazard and a short observation window is dominated by the fast-churning half — you are watching the months when discount customers are still leaving. A long window also captures the later stretch where only full-price customers remain. The same mixture therefore reads as a **higher** hazard when you observe it briefly. Young cohorts still look worse than they are.

**Within acquisition type (right).** Compute the hazard inside a homogeneous segment and the trend disappears: full-price LTV by cohort has r = **−0.11** against months observed — no relationship with age at all. The remaining wobble ($296–$339, ±7%) is sampling noise, not signal — each of those cohort estimates rests on only 56–106 full-price churn events, i.e. a range of ±19–26% on its own. The wobble is about a third the width of the uncertainty around it.

So the fix is the same as everywhere else in this exercise: **don't average across a mix.** The range is the other half of the answer — carry it, and don't read a story into cohort-to-cohort movement that sits inside it. Every cohort here rests on 306–442 churn events, so every range is ±9–11%; the $98–$122 spread across cohorts is barely wider than one cohort's own range.

## 2. LTV by acquisition type — the real driver

| Segment | n | Churn events | Monthly churn | Exp. lifetime | LTV | LTV range | CAC | LTV:CAC |
|---|---|---|---|---|---|---|---|---|
| **full_price** | 2,425 | 507 | 3.1%/mo | ~32.3 mo | **~$316** | $290 – $347 | ~$22.22 | **~14.2×** |
| **discount** | 2,375 | 1,834 | 18.2%/mo | ~5.5 mo | **~$52** | $49 – $54 | ~$19.43 | **~2.7×** |

Full-price customers are worth **~6.1× more**. Note the CACs are nearly identical (~$22 vs ~$19) — **you pay about the same for both.** The entire difference is in what you get. Discount customers churn six times faster and land under a 3× LTV:CAC bar, so they barely clear their own acquisition cost once margin is applied.

The ranges do not come close to touching, so this is the one finding you can state without hedging. They are also asymmetric in an instructive way: discount LTV is pinned to ±5% by 1,834 churn events, while full_price, built on 507 because those customers mostly haven't churned yet, carries ±9%. **The better segment is always the less certain one.** That is censoring, not sloppiness.

## 3. The geography trap (a confound)

Raw LTV by geo *looks* like geography decides value:

| geo | n | LTV (raw) | LTV range | % discount-acquired |
|---|---|---|---|---|
| CA | 765 | ~$161 | $144 – $183 | 25% |
| US | 1,625 | ~$128 | $119 – $138 | 40% |
| UK | 1,209 | ~$113 | $104 – $123 | 47% |
| **IN** | 1,201 | **~$69** | $64 – $74 | **81%** |

IN's range clears every other geo's by a wide margin, and CA's sits above all three — so the raw gap is real, it just isn't *about geography*. (UK and US do overlap, which is your first hint the ordering is softer than the point estimates look.) Split **within** acquisition type and it all but disappears:

| geo | discount LTV | range | full_price LTV | range | full_price churn events |
|---|---|---|---|---|---|
| CA | ~$49 | $42 – $58 | ~$311 | $263 – $380 | 120 |
| IN | ~$52 | $49 – $56 | ~$325 | **$252 – $456** | **48** |
| UK | ~$53 | $48 – $58 | ~$304 | $260 – $366 | 138 |
| US | ~$50 | $46 – $55 | ~$325 | $285 – $379 | 201 |

An IN full-price customer (~$325) is worth *more* than a Canadian one (~$311). The spread across all four geos is **7.0% within full_price and 8.2% within discount** — and every one of those eight ranges overlaps every other in its column, so there is no evidence any geo differs from any other once you hold acquisition type fixed. **IN only looks low-value because 81% of its customers were acquired on discount, vs. 25% in CA.** Geography is a confound; **acquisition type is the driver.** See [`ltv-driver-chart.png`](ltv-driver-chart.png).

*What the chart shows: two panels side by side. Left, raw LTV by geography — CA $161, US $128, UK $113, and IN lowest at $69, each bar labelled with its discount share, IN cross-hatched to mark it as the outlier. Right, the same data split by acquisition type — full-price bars solid, discount bars hatched — where all four geographies land within 7% of each other on full-price customers and within 8% on discount. The visual point is that the dramatic left-hand gap tracks the discount share, not the geography.*

Say the thin cell out loud: **IN's full-price estimate rests on 48 churn events**, the fewest in the table, so its range runs $253–$453. It is enough to kill the "IN is a bad market" story — the range sits far above IN's raw $69 either way — but not enough to rank IN against US. Report it as "indistinguishable," not as a winner.

**Income is a second, weaker story — and only partly a confound.** Discount accounts for 68% of low-band customers vs. 26% of high-band, so most of the raw income gap is the same mix effect. A residual does survive inside full_price (~$247 low vs. ~$344 mid and ~$342 high), and part of it is real: higher bands pay a higher fee. Note the fee is *not* determined by the band — all three fees appear in all three bands — so you can separate price from income here rather than having to assume.

## 4. LTV vs CPA by channel — where cheap traffic is expensive

[`ltv-by-channel.csv`](ltv-by-channel.csv), sorted cheapest CPA first:

| Channel | n | % discount | Churn events | CPA | Blended LTV | LTV range | LTV:CAC |
|---|---|---|---|---|---|---|---|
| referral | 1,522 | 69% | 903 | **~$11.12** | **~$81** | $76 – $86 | **~7.2×** |
| search | 1,583 | 30% | 602 | ~$22.04 | ~$153 | $141 – $166 | ~6.9× |
| paid_social | 1,695 | 50% | 836 | ~$28.45 | ~$106 | $99 – $114 | ~3.7× |

**Referral is the cheapest traffic and the least valuable** — the case the brief asks you to find. Rank on CPA alone and you buy the lowest-LTV customers in the account, with the ranges nowhere near overlapping ($76–$86 against search's $142–$166). It is not that referral attracts worse people: its full-price customers are worth the same as everyone's. It is that **69% of referral volume arrives on a discount**, because the referral offer *is* a discount. Search costs **2.0× more per customer and returns 1.9× the LTV** on a 30% discount mix — that is what a justified high CPA looks like.

**Now the part that matters most, because it is where this analysis can fool you: the answer changes with the metric.**

| Optimize on | Winner | Why |
|---|---|---|
| Lowest CPA | referral | cheapest clicks — and the lowest-value customers |
| Highest LTV | **search** | 1.9× referral's value for 2.0× the cost |
| Highest LTV:CAC | **referral** | 7.2× vs 6.9× — a small denominator flatters the ratio |

Referral is *both* the trap on raw LTV and the leader on efficiency, and both readings are arithmetically correct. The ratio is the right lens when your budget is fixed and you want the most value per dollar; **raw LTV is the right lens when you have budget to deploy and want the most value, full stop** — and growth budgets are usually the second case. Note also how thin referral's ratio win is (7.2× vs 6.9×, ~4%) against how thick its LTV loss is (~47% below search): the efficiency edge is inside the noise, the value gap is not. So **pick and state your metric before you rank channels**, or someone will hand you the ranking that suits their argument.

paid_social loses on both — dearest CPA *and* a 3.7× ratio, the only channel near the 3× floor. That one needs no tie-breaking.

**High CPA on search is justified; low CPA on referral is not a bargain.** Same lesson as the geography trap, one level up: the channel isn't the problem, the **mix it delivers** is.

*(All LTV and ratio figures here carry the 65% margin. On gross revenue the ratios read 11.2× / 10.7× / 5.7× — bigger numbers, identical ranking, which is exactly why you state the margin instead of quietly dropping it.)*

## 5. The value signal (for the platform)

[`bidding-signal-upload.csv`](bidding-signal-upload.csv) — `segment, predicted_value, value_tier`. Format is generic on purpose; platform field specs change often, so learn the concept rather than this week's schema.

| Segment | Predicted LTV | CAC | LTV:CAC | Tier |
|---|---|---|---|---|
| full_price \| referral | $316 | $11.15 | 28.3× | high |
| full_price \| search | $316 | $22.09 | 14.3× | high |
| full_price \| paid_social | $316 | $28.44 | 11.1× | high |
| discount \| referral | $52 | $11.10 | 4.6× | mid |
| discount \| search | $52 | $21.94 | 2.3× | low |
| discount \| paid_social | $52 | $28.46 | 1.8× | low |

**The tiering rule** — state yours, because unlabelled tiers aren't actionable:

- **high** — LTV:CAC ≥ 6 · double the standard healthy bar, bid up
- **mid** — 3 ≤ LTV:CAC < 6 · healthy, hold and optimise
- **low** — LTV:CAC < 3 · below the payback bar, bid down

Two things to be explicit about, because the file alone won't tell a colleague either:

- **The cut is on LTV:CAC, not on `predicted_value`.** That is why `discount | referral` and `discount | search` both carry $51.50 and land in different tiers — same modelled lifetime, half the acquisition cost. If you tier on predicted value alone, every discount segment gets the same label and the signal loses the only thing that separates them.
- **The cuts are conventions, not findings.** 3× is the common payback bar once margin is in; 6× is simply double it. Move the cuts and the labels move — so publish the rule beside the file.

**Why LTV is pooled within acquisition type.** Split the hazard all the way down to segment and the cells stop being informative. Within full_price:

| | n | events | hazard | hazard range |
|---|---|---|---|---|
| **pooled** | 2,425 | 507 | 3.09% | 2.82 – 3.36% |
| \| referral | 467 | 92 | 2.92% | 2.32 – 3.52% |
| \| search | 1,103 | 234 | 3.14% | 2.74 – 3.54% |
| \| paid_social | 855 | 181 | 3.13% | 2.68 – 3.59% |

All three segment intervals contain the pooled estimate. There is **no evidence channel changes retention within an acquisition type** — so pool the hazard where it is well-powered and let segments differ on the thing that genuinely does differ: **CAC**. Publishing six separate hazards would ship noise as signal, which is the §1 mistake wearing a different hat.

## 6. The human call

[`allocation-note.md`](allocation-note.md). Headline: bid **up** on full-price acquisition everywhere, bid **down** on discount acquisition — and fix the **referral offer** rather than cutting referral, exactly as you fix IN's offer mix rather than cutting IN.

## 7. Limits

- **You are projecting years from months.** The longest tenure anywhere in this file is **10 months** (the oldest cohort; the newest reaches 5), yet full_price's expected lifetime comes out at **32.3 months**. At a 3.09% hazard only 8.7 of those 32.3 expected months fall inside the observation window, so **~73% of full_price LTV is extrapolation past the last data point** — no customer in the dataset has lived long enough to confirm month 11, let alone month 32. (Discount LTV is the opposite: at 18% churn, 87% of its modelled value lands inside 10 months, which is why $51.50 is the sturdier of the two numbers despite being the smaller one.) Constant hazard is doing all the work out there, and nothing in the range above prices that. It is the single largest source of error in this analysis, and it is not a statistical problem you can shrink with more rows — only more *time* fixes it. If the number has to support a spend decision now, sanity-check it against a bounded horizon (say a 12-month LTV) as well, where the projection is a stretch rather than a leap.
- **Young cohorts carry the most forecast risk** — least observed tenure, widest ranges, and the mixture bias in §1 works against them specifically.
- **Segment hazards are underpowered** below roughly 500 customers; hence the pooling in §5. The thinnest cell reported is IN full_price at **48 churn events** ($253–$453) — quoted to kill a bad story, not to rank a market. Re-estimate per segment once volume supports it.
- **The ranges cover sampling noise only.** They answer "how many churn events is this hazard built on," not "is constant hazard the right model" or "is 65% the right margin." Both of those move the numbers further than the ranges do.
- Geometric decay imposes a **constant** monthly hazard. Real churn is usually front-loaded, which would lower early-life LTV and raise it later.
- Validate against **held-out cohorts over time** — its own discipline.
- This is cohort value analysis, not audience/persona research.

## Common mistakes

- Using **average revenue-to-date** as LTV — it reads $103 for full_price against a modelled $316, because half the base hasn't churned yet.
- Computing **one blended hazard per cohort** and ranking on it — that is the §1 trap, and it penalises your newest cohorts.
- Reporting **revenue:CAC as LTV:CAC** — skipping the margin assumption inflates every ratio ~1.5×.
- Stopping at **"cut India"** — the headline read, and wrong; it's an acquisition-mix artifact.
- Stopping at **"shift budget to referral"** — cheapest CPA, worst blended value; the same mistake pointed the other way.
- **Ranking channels without naming the metric** — raw LTV crowns search, LTV:CAC crowns referral, and both are correct arithmetic. Pick the lens that matches the decision (fixed budget → ratio; budget to deploy → value) and say which you used.
- **Point estimates with no range**, so the youngest cohort and the 48-event cell look as certain as the oldest and largest.
- **Quoting the range as if it covered everything** — it covers churn-event sampling only, not the 32-months-from-10-months extrapolation, which is bigger.
- Shipping only the signal file **or** only the allocation note — the deliverable is both.
