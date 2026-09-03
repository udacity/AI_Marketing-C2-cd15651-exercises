# Solution — Can We Rely On It, and How Do We Tune It?

*Worked solution. Numbers computed by comparing the provided sample forecast against the held-out actuals. Artifacts: [`calibration-comparison.csv`](calibration-comparison.csv) and [`calibration-chart.png`](calibration-chart.png).*

## 1. Forecast vs. actuals

| Metric | Actual (avg) | Forecast mid (avg) | Miss | Actuals inside band |
|---|---|---|---|---|
| **CPA** | **$52.78** | $48.09 | **+9.8%** | ~47% of days |
| **CVR** | 2.993% | 2.992% | +0.0% | ~73% of days |

Day-by-day: [`calibration-comparison.csv`](calibration-comparison.csv). Chart (band vs actuals): [`calibration-chart.png`](calibration-chart.png).

## 2. Systematic bias vs. noise

- **CPA is systematically biased — and it drifts.** Actuals sit *above* the mid on **22 of 30 days**, and the gap **grows from ~+$2.3 in the first 10 days to ~+$7.9 in the last 10**. A consistent, widening, one-directional miss is systematic, not random scatter.
- **CVR is well-calibrated.** Actual ≈ forecast, inside the band most days.

**Diagnosis:** CVR being on-target while CPA runs high and climbs tells you the error lives on the **click side** (CTR/CPC), not conversion. The sample forecast assumed ad fatigue was slowing (~+$0.11/day); actuals show it accelerated (~+$0.36/day).

## 3. Reliability verdict (per metric)

- **CVR — yes, plan on it.** Accurate and stable; safe for next month's conversion assumptions.
- **CPA — yes, with caveats.** Directionally usable but runs ~10% optimistic and worsening. Budget on the **high end of the band**, not the mid, until the fatigue assumption is fixed.

## 4. Tuning levers for the next forecast

- **Recency-weight** the trend fit so recent (steeper) fatigue counts more.
- **Steepen the fatigue assumption** rather than extrapolating the gentle training slope.
- **Widen the CPA band** to reflect its larger, compounding error (CVR's band is fine).

## 5. Override conditions (rebuild, don't tune)

Throw the forecast out and rebuild if any of these break the learned pattern:

- A **price change** or new **promo** during the forecast window.
- A **creative refresh** that resets the fatigue curve.
- A **channel/audience change** that shifts the CPC regime.

## 6. One-line for the CFO

> "Plan next month on this: conversion is reliable, cost-per-order is running about 10% higher than forecast and worsening as our ads age — budget to the top of the range and we'll tighten the model by steepening the fatigue assumption. If we change price or refresh creative, we re-forecast."

## Common mistakes

- Calling the CPA miss "noise" — missing that it's directional and widening.
- Grading both metrics the same — CVR is fine, CPA is biased.
- Handing the CFO variance math instead of the call + the why.
- Confusing a tuning lever (adjust weighting) with an override (rebuild on a price change).
