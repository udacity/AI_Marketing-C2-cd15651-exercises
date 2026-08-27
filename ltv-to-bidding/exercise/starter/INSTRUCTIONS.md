# Forecast LTV, Compare Cohorts, Build the Value Signal

Steep runs a tea subscription, and not all customers are worth the same. Forecast lifetime value across cohorts, dig past the obvious attribute to the real driver of value, and produce two outputs: a bidding-signal upload the platform can optimize against automatically, and an allocation call that's your own decision.

Work in Claude Code. The dataset is [`steep_cohorts.csv`](steep_cohorts.csv) — cohorts carrying acquisition channel, geography, an income proxy (AOV band), and acquisition type (full-price vs. discount-acquired), with retention and revenue by period.

**Scope:** this is cohort-level value analysis (channel, geography, acquisition type), not persona-level "who they are as people." Stay in the cohort lane.

The data has a trap built in: the intuitive read (a low-LTV geography) is a *confound*. Digging past the obvious attribute to the actual driver is the exercise.

## What to produce

- An LTV forecast per cohort (stated decay assumption + confidence), shown as a chart or table.
- A comparison of LTV against CPA across channel and geography — where low CPA hides low LTV, and where high CPA is justified.
- A driver analysis: which attribute most strongly separates high- from low-value customers, and at least one case where the intuitive explanation (geography or income) is really a confound for a behavioral driver.
- The **value signal**: a formatted bidding-signal upload (segment + predicted value + value tier).
- The **human call**: a short allocation note — which channels/segments to bid up or down given predicted value and the real driver, not the demographic story.
- Stated limits.

## Requirements

- Model retention/churn and project forward. Reading "average revenue-to-date" as final LTV will badly under-value young cohorts whose best customers haven't finished their lifespans — account for that censoring.
- Follow the data to the real driver. Form a hypothesis, but let the data lead; don't stop at the first attribute that looks predictive, and control for more than one variable.
- Produce both outputs. The signal is what the platform optimizes automatically; the allocation note is the call the platform can't make. One without the other is half the deliverable.
- State the limits, including that young cohorts carry the most forecast risk and that these forecasts should be validated against held-out cohorts over time.

## Done when

Your driver analysis identifies the real separator of value rather than the demographic story that's easiest to see, and both the bidding signal and the allocation note follow from it.
