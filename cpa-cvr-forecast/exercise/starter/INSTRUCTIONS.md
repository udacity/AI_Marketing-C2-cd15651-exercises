# Forecast CPA and CVR, Model the Month

Steep needs to plan next month's budget. Build a 30-day forecast for **CPA** (the anchor metric you budget against) and **CVR** from 90 days of campaign data, handle the anomalies baked into the history, and translate the forecast into what next month's spend will actually buy.

Work in Claude Code. The dataset is [`steep_campaign_90day.csv`](steep_campaign_90day.csv) — daily spend, impressions, CPM, clicks, CTR, CPC, orders, CPA, CVR, and notes.

**Scope:** the data is campaign-level (spend, impressions, clicks, orders, and the rates derived from them). It does not include creative-level metrics like engagement rate or video hook rate, so don't go looking for those.

## What to produce

A forecast read-out containing:

- 30-day forecasts for CPA and CVR, each with low/mid/high ranges, shown as a chart or table.
- How you handled each anomaly in the history.
- The assumptions behind each forecast and what drives the confidence spread.
- A budget-to-orders translation: at the mid-case CPA, what does a given spend buy in orders next month, and where's the biggest risk?

## Requirements

- Have Claude Code describe the patterns *before* forecasting, and distinguish the discrete sale-week **event** from the ongoing creative-fatigue **trend**. They're handled differently: exclude the event from baseline; carry the trend forward.
- Give ranges, not point estimates, and state the assumptions behind each.
- CPA is the anchor. Don't stop at CVR — the budget decision rides on CPA.
- End with the budget/orders read-out. A forecast that doesn't say what the spend buys isn't finished.

## Done when

Your read-out shows how each anomaly was handled, gives defensible CPA and CVR ranges, and turns "here's next month's spend" into "here's what next month's spend will buy."
