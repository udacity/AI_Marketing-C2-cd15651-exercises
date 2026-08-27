# Worked Demo — Calibration Is Tuning, Not Grading

*The real content: the finished walkthrough the demo produces. Reflects the baked-in patterns of the provided dataset (per the instructor answer key), so it reveals the intended conclusions.*

## The goal isn't a report card

Load the actuals ([`steep_campaign_holdout_30day.csv`](../starter/steep_campaign_holdout_30day.csv)) against the forecast ([`steep_sample_forecast_30day.csv`](../starter/steep_sample_forecast_30day.csv)). The point isn't to grade the past — it's a tuning loop: forecast, validate, adjust, forecast better.

## Compute the variance

For each metric, compute variance vs. the forecast mid and check whether actuals landed inside the low/high band. Look across the whole window, not just the total.

## Find the systematic bias

Systematic bias is a gift. A consistent directional miss — actuals running above the mid, drifting further above as the month goes on — points straight at the lever to pull. That's different from random scatter around the mid, which tells you the band was about right.

## Diagnose the cause

Here the tell is which metric missed. If CVR is basically on-target while CPA runs high and keeps climbing, the error lives on the click side (CTR/CPC), not conversion — the forecast assumed fatigue would flatten, and it didn't.

## Turn it into a tuning lever

Name the specific change that would have caught it: weight recent data more heavily, assume a steeper fatigue trend, or widen the band on that metric next time.

## Show an override condition

Some events don't call for tuning — they call for a rebuild. A price change or a new promo breaks the pattern the model learned. Name one concretely so students know what one looks like.

## State the verdict

Can we rely on this to plan next month? Give the call and the one change you'll make before you do.

## Key takeaway

Calibration is how a forecast gets better over time. Every miss is either a reason to distrust the model or a lever to tune it — the skill is knowing which.
