# Worked Demo — Calibration Is Tuning, Not Grading

*The real content: the finished walkthrough the demo produces. Numbers computed by joining the provided sample CPM forecast to the held-out actuals, so it reveals the intended conclusions. Day-by-day: [`cpm-calibration.csv`](cpm-calibration.csv).*

## The goal isn't a report card

Load the held-out actuals ([`steep_campaign_holdout_30day.csv`](../exercise/starter/steep_campaign_holdout_30day.csv)) against the provided sample 30-day CPM forecast ([`sample-cpm-forecast-30day.csv`](sample-cpm-forecast-30day.csv)). The point isn't to grade the past — it's a tuning loop: forecast, validate, adjust, forecast better.

## Compute the variance

Join forecast to actuals day by day ([`cpm-calibration.csv`](cpm-calibration.csv)) and read two numbers, not one:

- **Actual CPM averaged $14.02** against a **forecast mid of $14.31** — a **−2.0% miss**. The forecast ran slightly *high*.
- **20 of 30 days landed inside the low/high band** — a ~67% in-band rate.

A 2% average miss looks like a rounding error. Don't stop there: the average hides the shape.

## Systematic, or noise?

Decide it by a stated rule, not by squinting at the chart — direction, persistence, and whether the gap drifts across the window.

- **Direction:** actuals sat at or below the mid on **23 of 30 days**, above on 7. One-sided.
- **Drift:** the gap is **−$0.32 across the first ten days and −$0.37 across the last ten**. Steady, not widening.
- Every day that broke the band broke it on the *low* side; none broke the top.

So: systematic, but flat. That combination is the whole lesson.

## Diagnose the cause

The forecast's **slope was right; its level sat a touch high**. Actual CPM ran $12.92–$14.77 and climbed at about the rate the model projected — inventory really did get more expensive through the month. It just started that climb from a base roughly thirty cents too costly.

That's a **level bias**, and it reads differently from a **drift bias**. A miss that *grows* across the window means the trend itself is wrong and needs steepening. A miss that holds steady means the trend is fine and only the starting point needs moving. Same one-directional error, different lever — which is why you test for drift before you reach for a fix.

## Turn it into a tuning lever

Shift the level, don't touch the trend: **re-baseline CPM about 2% lower (~$0.30)** and leave the slope alone. The band is about the right width — most days sit inside it, and the ones that don't all miss low, which is exactly what re-centering fixes. Steepening the trend here would make the next forecast *worse*.

## Show an override condition

Some misses don't call for tuning — they call for a rebuild. An auction-side shock does that: a new placement type entering the mix, or a competitor's seasonal budget flooding the same inventory, resets the cost floor the model learned. Re-baselining a curve that no longer applies just produces a confident wrong number. Name one concretely so students know what one looks like.

## State the verdict

**Reliable — keep using it, nudge the level down slightly.** Deliver it the way a budget owner should hear it: *"CPM came in about 2% under forecast, steadily, all month. The model's read on the trend is good — we'll shave the starting level and keep planning on it."*

## Key takeaway

Calibration is how a forecast gets better over time. Every miss is either a reason to distrust the model or a lever to tune it — the skill is knowing which, and which part of the model to reach for.
