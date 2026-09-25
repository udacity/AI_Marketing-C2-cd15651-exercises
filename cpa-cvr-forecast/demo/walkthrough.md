# Worked Demo: Detect First, Then Forecast CPA

*The finished walkthrough the demo produces. The dataset is [`steep_campaign_90day_demo.csv`](steep_campaign_90day_demo.csv), 90 days of daily paid-media data for a DTC brand. It has no notes column on purpose: the demo has the model find what is unusual first, then the human supplies the business context. Numbers are computed from the data, so they are the intended ones; a live run will land close, not identical.*

## Detect before you explain

Don't tell the model what happened. Ask it to find what looks unusual, so you see what the numbers flag before you start explaining anything away. On this data it surfaces three things without being told:

- A **conversion spike, Sep 10 to 16**: orders roughly double, CVR jumps to 5 to 6 percent, and CPA drops to its lowest in the 90 days. Spend and CPM stay normal, so the move is on the conversion side only.
- A **gradual CTR decline from mid-September on**, with CPC drifting up alongside it. Not a spike, a sustained shift that does not revert.
- An **accelerating spend and CPM step-up in the last two weeks (Oct 18 to 29)**, where CPA climbs to the worst values in the set.

## Add the business context

The model can see that something changed. It cannot know why. That part is the human's job, and it is the point of the demo:

- The Sep 10 to 16 conversion spike was a **promotional week**, 20 percent off sitewide.
- The late-October spend and CPM climb was an **end-of-quarter budget ramp**: more money pushed into the auction raised what we paid for impressions.
- One the data cannot show at all: we were **between performance-marketing agencies** recently, which held execution back for a stretch. It is resolved now, so going forward we would expect to run a little more efficiently than the raw recent trend implies.

The first two sit in the numbers. The third lives only in the marketer's head, and briefing the model on what it cannot infer is the skill.

## Decide what carries into the next 30 days

For each pattern, ask one question: will it be true again next month? If yes, it belongs in the forecast. If no, it comes out of the baseline.

- **Promo week**: nothing scheduled next month, so exclude it from the baseline trend. Left in, it makes CPA look better than it will be.
- **End-of-quarter ramp**: next month is not a quarter end, so exclude it too. This is a controllable input, not a trend to extrapolate.
- **Creative fatigue** (the gradual CTR decline): ongoing, so carry it forward. Do not forecast a flat line.
- **Agency transition**: resolved, so nudge the baseline modestly more efficient than the naive trend, and label that a stated assumption, not a data-derived result.

## Forecast CPA

Fit a linear trend to daily CPA on the baseline days only (Aug 1 to Sep 9 and Sep 17 to Oct 17), excluding the promo week and the ramp. That trend captures the fatigue drift: CPA rising about $0.22 a day. Extrapolate it 30 days forward, then give three cases that differ only in how much credit the resolved-agency assumption gets:

| Case | 30-day avg CPA | What it assumes |
|---|---|---|
| High | ~$49.9 | Pure trend, no efficiency credit yet (resolution unproven until it shows in the data) |
| Mid | ~$48.4 | Trend plus a small 3% efficiency nudge for the resolved transition |
| Low | ~$47.4 | Trend plus a slightly larger 5% nudge, the optimistic end of the same assumption |

All three share the identical trend and slope. They differ only on the one lever the human introduced, which is exactly what makes them a defensible range rather than three guesses. Day-to-day actuals will still bounce roughly plus or minus $3 to 6 around whichever line lands.

One honest flag: the non-promo, non-ramp days from mid-September on run above the fitted line, so the series may be curving upward. If fatigue is accelerating rather than staying linear, the high case understates the risk, and a curved fit would capture it.

## Turn it into a decision

That CPA range is what the budget plans against. It says what an order is likely to cost next month, so you can decide whether to hold spend, put more behind it, or move some elsewhere. One caveat if you scale up: CPA will not hold flat. Bigger budgets buy pricier inventory and efficiency slips, which is what the quarter-end ramp already showed. So spending more is its own forecast, not this same cost stretched across a bigger budget.

## Key takeaway

Forecasting is fast. The judgment is the job: let the model find what is unusual, supply the context it cannot see, decide together what carries forward, and end on what the number means for the budget.
