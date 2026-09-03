# Solution — Forecast LTV, Compare Cohorts, Build the Value Signal

*Worked solution. LTV modelled from `steep_cohorts.csv` (4,800 customers, six monthly cohorts) with a churn-hazard method. Artifacts: [`ltv-by-cohort.csv`](ltv-by-cohort.csv), [`ltv-by-acqtype.csv`](ltv-by-acqtype.csv), [`ltv-by-geo.csv`](ltv-by-geo.csv), [`bidding-signal-upload.csv`](bidding-signal-upload.csv), [`ltv-driver-chart.png`](ltv-driver-chart.png), and the allocation note [`allocation-note.md`](allocation-note.md).*

## Method (stated assumptions)

**51% of the base is still active**, so revenue-to-date is a floor, not a lifetime. Don't average it. Instead:

- **Monthly churn hazard** = churned ÷ total observed customer-months (per segment).
- **Expected lifetime** = 1 ÷ hazard (geometric).
- **Predicted LTV** = **gross margin** × average monthly fee × expected lifetime.

Two assumptions to state out loud, because the numbers move if you disagree:

- **Gross margin = 65%.** Steep ships tea, so a subscription dollar is not a margin dollar. Skip this and you are computing *revenue*-to-CAC and labelling it LTV:CAC, which flatters every ratio by ~1.5×.
- **No discount rate.** Lifetimes here top out near 32 months; discounting to present value moves the numbers a few percent and changes no ranking. Add it if you extend the horizon.

**Confidence** is the 95% interval on each hazard (standard error ≈ √events ÷ customer-months), inverted into an LTV band.

## 1. LTV per cohort — and why the obvious version is still wrong

[`ltv-by-cohort.csv`](ltv-by-cohort.csv). Three columns, three different answers to the same question:

| Cohort | n | Months obs. | Avg revenue-to-date | Blended LTV | 95% band | full_price LTV |
|---|---|---|---|---|---|---|
| 2025-01 | 800 | 10 | $103.98 | ~$122 | $111 – $134 | ~$339 |
| 2025-02 | 800 | 9 | $94.61 | ~$111 | $101 – $122 | ~$296 |
| 2025-03 | 800 | 8 | $83.86 | ~$98 | $90 – $108 | ~$300 |
| 2025-04 | 800 | 7 | $79.87 | ~$117 | $106 – $131 | ~$323 |
| 2025-05 | 800 | 6 | $68.67 | ~$98 | $89 – $109 | ~$308 |
| 2025-06 | 800 | 5 | $61.85 | ~$104 | $93 – $117 | ~$335 |

**Read the three columns as a sequence of fixes.**

**Revenue-to-date (worst).** Falls from $104 to $62, almost perfectly with cohort age (r = **−0.99**). That is not six cohorts of differing quality — it is the same customers observed for ten months versus five. Rank cohorts on this and you will defund your newest acquisition for the crime of being new.

**Blended hazard (better, still biased).** Modelling churn removes most of it, but a downward tilt survives (r = **−0.59**). This one is subtle and worth understanding: your cohort is a *mixture* of a ~3%/mo segment and an ~18%/mo segment. Pool them into one hazard and a short observation window is dominated by the fast-churning half — you are watching the months when discount customers are still leaving. A long window also captures the later stretch where only full-price customers remain. The same mixture therefore reads as a **higher** hazard when you observe it briefly. Young cohorts still look worse than they are.

**Within acquisition type (right).** Compute the hazard inside a homogeneous segment and the trend disappears: full-price LTV by cohort has r = **+0.11** — no relationship with age at all. The remaining wobble ($296–$339) is sampling noise, not signal.

So the fix is the same as everywhere else in this exercise: **don't average across a mix.** The band width is the other half of the answer — carry it, and don't read a story into cohort-to-cohort movement that sits inside it.

## 2. LTV by acquisition type — the real driver

| Segment | n | Monthly churn | Exp. lifetime | LTV | CAC | LTV:CAC |
|---|---|---|---|---|---|---|
| **full_price** | 2,425 | 3.1%/mo | ~32.3 mo | **~$316** | ~$22.22 | **~14.2×** |
| **discount** | 2,375 | 18.2%/mo | ~5.5 mo | **~$52** | ~$19.43 | **~2.7×** |

Full-price customers are worth **~6.1× more**. Note the CACs are nearly identical (~$22 vs ~$19) — **you pay about the same for both.** The entire difference is in what you get. Discount customers churn six times faster and land under a 3× LTV:CAC bar, so they barely clear their own acquisition cost once margin is applied.

## 3. The geography trap (a confound)

Raw LTV by geo *looks* like geography decides value:

| geo | n | LTV (raw) | % discount-acquired |
|---|---|---|---|
| CA | 765 | ~$161 | 25% |
| US | 1,625 | ~$128 | 40% |
| UK | 1,209 | ~$113 | 47% |
| **IN** | 1,201 | **~$69** | **81%** |

IN looks like the worst market by a factor of 2.3. Split **within** acquisition type and geography all but disappears:

| geo | discount LTV | full_price LTV |
|---|---|---|
| CA | ~$49 | ~$311 |
| IN | ~$52 | ~$325 |
| UK | ~$53 | ~$304 |
| US | ~$50 | ~$325 |

An IN full-price customer (~$325) is worth *more* than a Canadian one (~$311). The spread across all four geos is **7.0%**, inside the confidence bands. **IN only looks low-value because 81% of its customers were acquired on discount, vs. 25% in CA.** Geography is a confound; **acquisition type is the driver.** See [`ltv-driver-chart.png`](ltv-driver-chart.png).

**Income is a second, weaker story — and only partly a confound.** Discount accounts for 68% of low-band customers vs. 26% of high-band, so most of the raw income gap is the same mix effect. A residual does survive inside full_price (~$247 low vs. ~$344 mid and ~$342 high), and part of it is real: higher bands pay a higher fee. Note the fee is *not* determined by the band — all three fees appear in all three bands — so you can separate price from income here rather than having to assume.

## 4. LTV vs CPA by channel — where cheap traffic is expensive

| Channel | n | CPA | % discount | Blended LTV | LTV:CAC |
|---|---|---|---|---|---|
| referral | 1,522 | **~$11.12** | 69% | **~$81** | ~7.2× |
| search | 1,583 | ~$22.04 | 30% | ~$153 | ~6.9× |
| paid_social | 1,695 | ~$28.45 | 50% | ~$106 | ~3.7× |

**Referral is the cheapest traffic and the least valuable** — the case the brief asks you to find. It is not that referral attracts worse people: its full-price customers are worth the same as everyone's. It is that **69% of referral volume arrives on a discount**, because the referral offer *is* a discount. Search costs twice as much per customer and returns a blended LTV nearly 90% higher on a 30% discount mix.

**High CPA on search is justified; low CPA on referral is not a bargain.** Same lesson as the geography trap, one level up: the channel isn't the problem, the **mix it delivers** is.

## 5. The value signal (for the platform)

[`bidding-signal-upload.csv`](bidding-signal-upload.csv) — `segment, predicted_ltv, value_tier`. Format is generic on purpose; platform field specs change often, so learn the concept rather than this week's schema.

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

**Why LTV is pooled within acquisition type.** Split the hazard all the way down to segment and the cells stop being informative. Within full_price:

| | n | events | hazard | 95% CI |
|---|---|---|---|---|
| **pooled** | 2,425 | 507 | 3.09% | 2.82 – 3.36% |
| \| referral | 467 | 92 | 2.92% | 2.32 – 3.52% |
| \| search | 1,103 | 234 | 3.14% | 2.74 – 3.54% |
| \| paid_social | 855 | 181 | 3.13% | 2.68 – 3.59% |

All three segment intervals contain the pooled estimate. There is **no evidence channel changes retention within an acquisition type** — so pool the hazard where it is well-powered and let segments differ on the thing that genuinely does differ: **CAC**. Publishing six separate hazards would ship noise as signal, which is the §1 mistake wearing a different hat.

## 6. The human call

[`allocation-note.md`](allocation-note.md). Headline: bid **up** on full-price acquisition everywhere, bid **down** on discount acquisition — and fix the **referral offer** rather than cutting referral, exactly as you fix IN's offer mix rather than cutting IN.

## 7. Limits

- **Young cohorts carry the most forecast risk** — least observed tenure, widest bands, and the mixture bias in §1 works against them specifically.
- **Segment hazards are underpowered** below roughly 500 customers; hence the pooling in §5. Re-estimate per segment once volume supports it.
- Geometric decay imposes a **constant** monthly hazard. Real churn is usually front-loaded, which would lower early-life LTV and raise it later.
- Validate against **held-out cohorts over time** — its own discipline.
- This is cohort value analysis, not audience/persona research.

## Common mistakes

- Using **average revenue-to-date** as LTV — it reads $103 for full_price against a modelled $316, because half the base hasn't churned yet.
- Computing **one blended hazard per cohort** and ranking on it — that is the §1 trap, and it penalises your newest cohorts.
- Reporting **revenue:CAC as LTV:CAC** — skipping the margin assumption inflates every ratio ~1.5×.
- Stopping at **"cut India"** — the headline read, and wrong; it's an acquisition-mix artifact.
- Stopping at **"shift budget to referral"** — cheapest CPA, worst blended value; the same mistake pointed the other way.
- **Point estimates with no bands**, so the youngest cohort looks as certain as the oldest.
- Shipping only the signal file **or** only the allocation note — the deliverable is both.
