# Can We Rely On It, and How Do We Tune It?

Next month's budget will be planned off Steep's forecasting approach. Validate the provided CPA and CVR forecasts against the held-out actuals, then answer the two questions a decision-maker actually has: can we trust this to plan on, and how do we make the next forecast better?

Work in Claude Code. Use:

- [`steep_campaign_holdout_30day.csv`](steep_campaign_holdout_30day.csv) — the actuals for the forecast period.
- [`steep_sample_forecast_30day.csv`](steep_sample_forecast_30day.csv) — the CPA/CVR forecast to validate.

## What to produce

A short calibration report a non-technical decision-maker (think CFO) could act on, covering CPA and CVR:

- A forecast-vs-actual comparison shown as a chart or table (forecast band vs. actuals): variance, and whether actuals landed inside each range.
- The systematic bias per metric, with a diagnosis of the cause (did the sale-week handling help or hurt? did fatigue keep accelerating?).
- A reliability verdict per metric: can this be trusted to plan next month — yes, no, or yes-with-caveats — and why.
- The tuning levers: specific adjustments that would make the next forecast more reliable.
- Override conditions: events that would invalidate the forecast and force a full rebuild rather than a tune.

## Requirements

- Distinguish a **systematic** (directional) miss from random scatter, and say which each metric is. Treating a real directional miss as mere noise is the trap to avoid.
- Diagnose per metric. CPA and CVR can behave differently, and which one misses tells you where the error lives.
- Write for a CFO: put in the verdict, the confidence, the one-line reason, and the recommended action. Keep out the raw variance math and model internals — they need the call and the why, not the calculations.
- Separate tuning levers (adjust the model) from override conditions (throw it out and rebuild). They're different responses to different kinds of miss.

## Done when

Your report answers both questions plainly — *can I plan on this?* and *how are we making it better?* — per metric, in language a non-technical decision-maker could act on.
