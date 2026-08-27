# Demo — Calibration Is Tuning, Not Grading

*Instructor demo brief. Estimated running time ~7 minutes. The full worked version is in [`../solution/walkthrough.md`](../solution/walkthrough.md).*

## Setup

- **Scenario:** Steep made a 30-day forecast and the actuals for that period are now in. The job isn't to grade the forecast — it's to decide whether to rely on it and how to tune the next one.
- **Tool:** Claude Code.
- **Inputs:**
  - [`steep_campaign_holdout_30day.csv`](steep_campaign_holdout_30day.csv) — the actuals for the forecast period.
  - [`steep_sample_forecast_30day.csv`](steep_sample_forecast_30day.csv) — the forecast to validate against them.

## What the demo demonstrates

1. Load actuals against the forecast; compute variance vs. the mid and whether actuals fell inside the band.
2. Find the systematic bias — is the miss directional across the window, or just scatter?
3. Diagnose the cause (e.g., fatigue kept accelerating and the model under-projected the drift).
4. Turn it into a tuning lever: what specific change would have caught it (steeper fatigue trend, recency weighting, wider band)?
5. Show one override condition: an event that would make you throw the forecast out and rebuild rather than tune it (a price change, a new promo).
6. State the verdict: can we rely on this to plan next month, and what we'll change before we do.

## Key takeaway

Calibration is how a forecast gets better over time. Every miss is either a reason to distrust the model or a lever to tune it — the skill is knowing which, and saying so plainly.
