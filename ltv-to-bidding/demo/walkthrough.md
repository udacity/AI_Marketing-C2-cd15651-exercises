# Worked Demo — From Cohort Curve to Bidding Signal

*The real content: the finished walkthrough the demo produces. Scoped to a single acquisition cohort — the demo shows the mechanism end to end; comparing segments to find the real driver of value is the exercise's job, not this one's.*

## LTV is a projection, not a number

Load [`steep_cohorts.csv`](../exercise/starter/steep_cohorts.csv) and have Claude Code describe what is actually in the file: one row per customer, with observed tenure in months and a status of `active` or `churned`. There is no retention curve to read — you build one. Churn events ÷ total observed tenure months gives a monthly churn hazard; carry the surviving fraction forward month by month and multiply by the average monthly fee for value. The decay is an assumption you state, not a shape you find.

## Project one cohort

Take the **2025-01 cohort: 800 customers, 438 churn events across 5,532 observed customer-months** — a **7.92% monthly churn hazard**. At an average fee of **$14.80** and a **65% gross margin** (state the margin out loud; a subscription dollar is not a margin dollar), project survival forward twelve months:

> **12-month LTV ≈ $76.37**, directionally **$73.60 – $79.29**.

Both halves matter. The decay assumption is **constant monthly hazard** — the same churn rate in month 12 as in month 1, which is a choice, not a finding. The range comes from how many churn events sit behind the hazard: relative precision ≈ 1 ÷ √events, so recompute at hazard × (1 ± 2 ÷ √events). 438 events buys about ±4%; a thin segment with 40 events would be four times looser. Chart the cumulative curve ([`cohort-ltv-curve.png`](cohort-ltv-curve.png)) so the flattening is visible.

## Name your horizon — it moves the number

Let the same hazard run uncapped and expected lifetime is 1 ÷ 7.92% ≈ **12.6 months** of survival value, which reads **~$122** for this cohort instead of $76.37. **Capping at twelve months gives up roughly 37% of the modelled value.** Neither number is wrong; they answer different questions, and "LTV" on its own doesn't say which one you mean. Pick the horizon that matches the payback window you plan against: if the spend has to earn back inside a year, the 12-month figure is the one you bid on, and the lifetime figure is upside you haven't observed yet.

## The strategic punchline

A platform optimizing for cheap conversions buys the customers who are cheap to buy, and nothing else. Suppose one source delivers customers at half the cost of another — the bidder chases the cheap one every time, even if the dearer customers turn out to be worth several times more over their life. **On lowest CPA alone you can end up buying your *worst* customers.** That is the case for value-based bidding: stop telling the platform what a conversion *costs* and start telling it what a conversion is *worth*.

The number you hand back here is the one this cohort owns: **$76.37 of 12-month value against $20.95 of acquisition cost — about 3.6× LTV:CAC.**

## Make the prediction actionable

A prediction only matters if it leaves the spreadsheet. Format the LTV as a representative bidding-signal upload:

```
segment / customer_id, predicted_value, value_tier
```

(Teach a generic value-signal shape, not exact current platform field specs — those change constantly.)

Show the tiering **rule** next to the file, or the tier is just an opinion. In [`bidding-signal-sample.csv`](bidding-signal-sample.csv) the cut is on LTV:CAC — **high ≥ 6×, mid 3–6×, low < 3×** — so this cohort's 3.6× lands **mid**: healthy, hold and optimise. Two things to say out loud. The cut is on the **ratio**, not on `predicted_value` alone, which is why two rows can carry the same predicted value and still tier differently — same modelled lifetime, different acquisition cost. And the cuts are **conventions, not findings**: 3× is the common payback bar once margin is in, 6× is simply double it. Move the cuts and the labels move, so publish the rule beside the file.

Then explain how the platform uses it: bidding up toward high-value profiles, down on low-value ones, automatically.

## The second output: the human call

The LTV forecast pays off two ways. Beyond the automatic signal, show the marketer's own allocation note — which cohorts to bid up or down. This is the judgment the platform can't make for you, and it's what the exercise asks students to write alongside the signal file.

## Key takeaway

The frontier isn't cheaper conversions — it's valuable ones. LTV forecasting closes the loop only when the prediction becomes a bidding signal the platform can act on.
