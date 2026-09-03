# Calibration Report — Can We Plan Next Month On This Forecast?

*For the budget decision-maker. Thirty days of actuals measured against the forecast we planned on. Day-by-day detail: [`calibration-comparison.csv`](calibration-comparison.csv). Band vs. actuals: [`calibration-chart.png`](calibration-chart.png).*

## The call

**Plan on the conversion rate. Do not plan on the mid-case cost per order — budget to the top of its range instead.**

| Metric | Forecast (avg) | Actual (avg) | Variance | Days inside the range | Verdict |
|---|---|---|---|---|---|
| **CPA** — cost per order | $48.10 | **$52.78** | **+9.75% worse than forecast** | 14 of 30 (~47%) | **Yes, with caveats** |
| **CVR** — conversion rate | 2.992% | 2.993% | **+0.04%** | 22 of 30 (~73%) | **Yes — plan on it** |

Conversion came in almost exactly as forecast. Cost per order came in about **10% higher**, and the forecast only contained it on **fewer than half the days** — so the range itself was too narrow, not just the midpoint too low.

## Is the miss real, or is it noise?

We treat a miss as **systematic** only if it points one way, persists, and drifts. Random scatter does none of those.

- **CPA — systematic, and worsening.** Actuals landed above the forecast midpoint on **22 of 30 days**, and the gap widened from **+$2.28** per order across the first ten days to **+$7.91** across the last ten. One direction, most days, growing. That is a model error, not bad luck.
- **CVR — noise.** The average is on target to within a rounding error, and misses fall on both sides of the forecast. The days outside the band are scatter, not drift. Nothing to fix here.

## What caused it

**Our ads aged faster than the forecast assumed.** The forecast expected cost per order to creep up gently as the month wore on. It climbed about **three times that fast** — and because the effect compounds day after day, that alone accounts for the widening gap.

The error sits **before the sale, not at it.** Conversion held steady while cost per order climbed, which means we were not losing customers once they arrived — we were paying more to get them there. Across the window, **click-through fell about 12%** from the first ten days to the last, and **cost per click rose about 18%** over the same stretch, while the share of visitors who bought did not move. The forecast's conversion assumption was sound; its assumption about ad fatigue slowing down was not.

## Reliability verdict, per metric

- **CVR — yes, plan on it.** *High confidence.* Accurate and stable across the full window. Safe to hold as next month's conversion assumption without adjustment.
- **CPA — yes, with caveats.** *Moderate confidence in the direction, low in the level.* The shape of the forecast is right and cost per order is genuinely rising; the forecast simply understates how fast. **Budget at the high end of the band, not the mid**, until the fatigue assumption is corrected. Treat the midpoint as a best case.

**What that means for the plan:** at the mid-case CPA the same budget buys about 9% fewer orders than the forecast promised. Plan volume off the top of the range and the forecast is safe to use now; plan it off the midpoint and we will miss the order target.

## Tuning levers — fix the model, keep using it

These address a model that is right in shape and wrong in degree:

- **Steepen the ad-fatigue assumption** to the rate we actually observed, rather than extrapolating the gentler slope from the training window.
- **Recency-weight the trend fit** so the most recent weeks — where fatigue is steepest — carry more influence than the oldest ones.
- **Widen the CPA band** to reflect an error that compounds over the horizon. Fewer than half of days landing in-band means the band is mis-sized. CVR's band is correctly sized; leave it.
- **Forecast the click side explicitly** — project click-through rate and cost per click, then derive cost per order from them, instead of trending cost per order directly. That is where the error originated, so that is where it should be modelled.

## Override conditions — rebuild, don't tune

Tuning assumes next month behaves like last month. If any of these happen, the pattern the model learned no longer exists and the forecast should be thrown out and rebuilt, not adjusted:

- **A price change or a new promotion** during the forecast window. Both reset the relationship between spend and orders.
- **A creative refresh.** This resets the fatigue curve outright — the trend we are extrapolating disappears, and a steeper assumption would then be wrong in the opposite direction.
- **A channel or audience change** that shifts the cost-per-click regime, since that is the mechanism driving the miss.

## Limits

- This is **one 30-day window**. It is enough to establish that cost per order is biased and conversion is not; it is not enough to fix the fatigue rate precisely.
- **No promotion ran during the holdout period**, so this validation says nothing about how well the forecast handles promotional weeks. That remains untested.

## In one line

> "Plan next month on this: conversion is reliable, cost per order is running about 10% higher than forecast and worsening as our ads age — budget to the top of the range, and we will tighten the model by steepening the fatigue assumption. If we change price or refresh creative, we re-forecast from scratch."
