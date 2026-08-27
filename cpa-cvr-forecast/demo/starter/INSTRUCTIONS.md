# Demo — Forecast the Easy Metric, Then Name the Hard One

*Instructor demo brief. Estimated running time ~8 minutes. The full worked version is in [`../solution/walkthrough.md`](../solution/walkthrough.md).*

## Setup

- **Scenario:** Steep, a DTC tea brand, runs paid social to drive orders. The marketer has 90 days of daily data and needs a 30-day forward forecast to plan next month's budget.
- **Tool:** Claude Code.
- **Input:** [`steep_campaign_90day.csv`](steep_campaign_90day.csv) — daily spend, impressions, CPM, clicks, CTR, CPC, orders, CPA, CVR, and notes.

**Scope:** the data is campaign-level. It does not include creative-level metrics like engagement rate or video hook rate.

## What the demo demonstrates

1. Load the CSV; ask Claude Code to describe trends and call out the notes-flagged events (sale week, spend ramp) *before* forecasting.
2. Build a 30-day CPM forecast with low/mid/high ranges and stated assumptions, and produce a simple chart.
3. Interrogate the output — surface its assumptions, then push back on one number that looks off. Treat the first pass as a draft to critique, not a finished forecast.
4. Pivot: show how CPA = f(spend, CTR, CPC, CVR), decomposing it so students see why it can't be extrapolated as a single line.
5. Point at the creative-fatigue trend and the sale spike: which do you exclude, which do you carry forward?
6. Translate the mid-case into plain terms: at this CPA, a given monthly spend buys roughly this many orders.

## Key takeaway

Forecasting is fast; the discipline is human — describe before you project, always give a range, state assumptions. CPM is easy and mostly irrelevant; CPA is hard and the one you budget against.
