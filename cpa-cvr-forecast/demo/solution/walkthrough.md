# Worked Demo — Forecast the Easy Metric, Then Name the Hard One

*The real content: the finished walkthrough the demo produces. Reflects the baked-in patterns of the provided dataset (per the instructor answer key), so it reveals the intended conclusions.*

## Describe before you project

Load [`steep_campaign_90day.csv`](../starter/steep_campaign_90day.csv) and ask Claude Code to describe the data first — trends, seasonality, and the notes-flagged events. Two events are flagged in the notes: a promo/sale week and an end-of-quarter spend ramp. Never forecast off a sale spike or a fatigue drift you haven't named.

## Forecast CPM (the easy one)

CPM is easy because it's essentially one cost/inventory trend. Build a 30-day CPM forecast as a **range** — low / mid / high — with the reasoning behind the spread, and chart it. A credible forecast is never a lone point estimate.

## Interrogate the draft

Ask Claude Code to surface its assumptions, then push back on one number that looks off. The first pass is a draft to critique, not a finished forecast to accept.

## Name the hard one: CPA

Pivot to CPA and decompose it: **CPA is composed**, moving when CTR, CPC, or CVR move. That's why it can't be extrapolated as a single line the way CPM can — forecasting it means understanding its drivers.

Then point at the two patterns and decide their treatment:

- **Creative fatigue** — CTR eroding gradually — is a *trend* you carry forward.
- **The sale week** is a discrete *event* you exclude from the baseline, or it drags the trend line optimistic.

## Payoff: budget to orders

Translate the mid-case into plain terms: at this CPA, a given monthly spend buys roughly this many orders. That's the budget/orders read-out the exercise asks students to produce.

## Key takeaway

Forecasting is fast; the discipline is human — describe before you project, always give a range, state assumptions. And know which metric drives the decision: CPM is easy and mostly irrelevant, CPA is hard and the one you budget against.
