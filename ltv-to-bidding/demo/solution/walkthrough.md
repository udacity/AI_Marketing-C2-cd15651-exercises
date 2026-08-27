# Worked Demo — From Cohort Curve to Bidding Signal

*The real content: the finished walkthrough the demo produces. Reflects the baked-in patterns of the provided dataset (per the instructor answer key), so it reveals the intended conclusions.*

## LTV is a curve, not a number

Load [`steep_cohorts.csv`](../starter/steep_cohorts.csv) and have Claude Code describe the retention and revenue curves across cohorts. LTV forecasting is curve projection: you model the retention/revenue curve forward and account for its decay, rather than reading a single number off the data.

## Project one cohort

Project one acquisition cohort's curve forward to a 12-month LTV, stating the decay assumption and the confidence range, and chart it.

## The strategic punchline

This cohort's CPA looked "expensive" — but its LTV makes it your best-acquired group. Optimizing for lowest CPA can acquire your *worst* customers. Value-based bidding tells the platform to chase predicted value, not cheap clicks.

## Make the prediction actionable

A prediction only matters if it leaves the spreadsheet. Format the LTV as a representative bidding-signal upload:

```
segment / customer_id, predicted_value, value_tier
```

(Teach a generic value-signal shape, not exact current platform field specs — those change constantly.)

Then explain how the platform uses it: bidding up toward high-value profiles, down on low-value ones, automatically.

## The second output: the human call

The LTV forecast pays off two ways. Beyond the automatic signal, show the marketer's own allocation note — which cohorts to bid up or down. This is the judgment the platform can't make for you, and it's what the exercise asks students to write alongside the signal file.

## Key takeaway

The frontier isn't cheaper conversions — it's valuable ones. LTV forecasting closes the loop only when the prediction becomes a bidding signal the platform can act on.
