# Demo — From Cohort Curve to Bidding Signal

*Instructor demo brief. Estimated running time ~10 minutes. The full worked version is in [`../solution/walkthrough.md`](../solution/walkthrough.md).*

## Setup

- **Scenario:** Steep runs a subscription. Some customers churn after one box, some stay for years. The marketer wants to predict lifetime value by cohort and feed those predictions back into the ad platforms so bidding optimizes for *valuable* customers, not just cheap conversions.
- **Tool:** Claude Code.
- **Input:** [`steep_cohorts.csv`](steep_cohorts.csv) — customers grouped by acquisition month, channel, geo, income band, acquisition type, with retention and revenue by period.

**Scope:** this is cohort-level value analysis (channel, geography, acquisition type), not persona-level "who they are as people."

## What the demo demonstrates

1. Load the cohort data; have Claude Code describe retention and revenue curves across cohorts.
2. Project one cohort's curve forward to a 12-month LTV, stating the decay assumption and confidence, and chart the curve.
3. Show the punchline: this cohort's CPA looked "expensive," but its LTV makes it your best-acquired group.
4. Format the first output as a representative bidding-signal upload (segment + predicted value + value tier).
5. Explain how the platform uses it: bidding up toward high-value profiles, down on low-value ones.
6. Show the second output: the marketer's own allocation call — a short note on which cohorts to bid up or down. This is the judgment the platform can't make.

## Key takeaway

The frontier of AI-augmented performance marketing isn't cheaper conversions — it's *valuable* ones. LTV forecasting closes the loop only when the prediction becomes a bidding signal the platform can act on.
