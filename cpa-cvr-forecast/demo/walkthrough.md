# Worked Demo — Forecast the Easy Metric, Then Name the Hard One

*The real content: the finished walkthrough the demo produces. The CPM forecast is computed from the provided dataset, so those numbers are the intended ones. The demo stops short of the exercise's CPA work on purpose: it names the decisions and leaves them open — making them is the learner's job.*

## Describe before you project

Load [`steep_campaign_90day.csv`](../exercise/starter/steep_campaign_90day.csv) and ask Claude Code to describe the data first — trends, seasonality, and the notes-flagged events. Two events are flagged in the notes: a promo/sale week and an end-of-quarter spend ramp. Never forecast off a sale spike or a fatigue drift you haven't named.

## Forecast CPM (the easy one)

CPM is easy because it's essentially one cost/inventory trend. Build a 30-day CPM forecast as a **range** — low / mid / high — with the reasoning behind the spread, and chart it. A credible forecast is never a lone point estimate.

Day-by-day: [`forecast-cpm-30day.csv`](forecast-cpm-30day.csv). Chart: [`cpm-forecast-chart.png`](cpm-forecast-chart.png) — 30-day mid averages **$14.31**.

*What the chart shows: the 90 training days with promo week (squares) and the end-of-quarter ramp (triangles) marked as excluded from the fit, then the 30-day forecast mid (dashed) rising from $13.97 to $14.65 inside its ±1σ band. The two excluded windows are visibly off-trend, which is the point — they are why the fit is drawn on the remaining days.*

## Interrogate the draft

Ask Claude Code to surface its assumptions, then push back on one number that looks off. The first pass is a draft to critique, not a finished forecast to accept.

## Name the hard one: CPA

Pivot to CPA and decompose it: **CPA is composed**, moving when CTR, CPC, or CVR move. That's why it can't be extrapolated as a single line the way CPM can — forecasting it means understanding its drivers.

Then put two of CPA's moving parts on screen and leave them there:

- **Creative fatigue** — CTR eroding gradually across the campaign's life.
- **The sale week** — a spike bounded to one window.

Ask the question; don't answer it. *Which of these do you carry forward into the next 30 days, and which do you leave out of the baseline?* One is a gradual drift, the other sits inside a boundary you can draw — different shapes, so the same treatment can't be right for both. Which gets which, and why, is the call.

## Why the call matters

Say out loud what rides on it. Every number downstream — the CPA mid, the spread around it, and the budget read-out that comes off that mid — inherits whatever you decided here. Get the treatment wrong and the arithmetic still comes out clean; it's just built on a baseline that never happened. That's why this is a judgement you state and defend in your assumptions, not a setting you pick.

Stop here. Naming the decision is the demo's job. Making it — for these patterns and any others in the 90 days — is the exercise.

## Key takeaway

Forecasting is fast; the discipline is human — describe before you project, always give a range, state assumptions. And know which metric drives the decision: CPM is easy and mostly irrelevant, CPA is hard and the one you budget against.
