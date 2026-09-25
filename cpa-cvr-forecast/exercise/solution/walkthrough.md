# Solution: Forecast Next Month's CPC

*Worked solution, one strong example. Numbers are computed from [`steep_traffic_90day.csv`](../starter/steep_traffic_90day.csv); a reasonable submission will land close, not identical, depending on method and band width. What matters is that the three patterns are handled on their own terms and the two that pull against each other are reconciled, not that the CPC lands on a specific number. Charts render live in the tool, so read the figures off the chart in your session; every number below also appears in this text.*

## 1. Describe the data first (before forecasting)

Have the model review the 90 days (Mar 1 to May 29) before any forecasting. Three patterns show up, and they map onto the three business facts in the brief.

- **Seasonal decline, Mar 1 to early May.** CTR falls almost monotonically from ~2.9% to ~1.75%, and CPC nearly doubles from ~$0.40 to ~$0.72 over the same window. A sustained slide, not noise.
- **A step-change in early May.** Around May 6 the metrics jump: CTR back up to ~2.5%, CPC back down to ~$0.48. This does not resume the old decline afterward, it holds at a new, better plateau through May 29.
- **A one-off spend spike, May 6 to 12.** Daily spend doubles (from ~$1,000 to ~$1,900 to $2,200) for seven days, then drops back to baseline in a single day. CPM ticks up slightly during that window, a byproduct of the heavier spend.

## 2. Map each pattern to the business context, and set its treatment

The brief gives you three facts. Line them up:

- **Seasonal softening** explains the Mar to April decline. It is a genuine ongoing trend. **Carry it forward**, June is deeper into summer, so demand keeps softening.
- **The new product launch** explains the early-May step-up. Split it in two. The **durable lift** (the new, higher CTR plateau) is the product staying in the line, so **carry the new level**. The **launch-week spend spike** is a one-off push, so **exclude it from the baseline**, or it overstates normal spend.
- **The competitor tea launch** is nowhere in the data. It is a forward-looking risk, so **adjust the forecast**, expect upward CPM pressure in June, layered on as a stated assumption.

The trap to avoid: treating the May step-up like the promo weeks taught elsewhere and excluding it. It is not a bounded event, it is a permanent shift, and the right move is to forecast off the post-launch plateau, not the pre-launch decline.

## 3. The 30-day forecast (June)

Anchor to the **post-launch plateau** (May 13 to 29): CTR ~2.51%, CPC ~$0.48, CPM ~$12.05, spend ~$1,000/day. From there, carry the seasonal CTR decline forward (about −0.0175 points per day, measured off the Mar to April slope) and add a small competitor CPM nudge. CPC is CPM divided by CTR, so a softening CTR and a firmer CPM both push CPC up.

| Case | June CPC (avg) | What it assumes |
|---|---|---|
| Low | ~$0.52 | Seasonal decline flattens, launch lift fully holds, competitor adds ~1% to CPM |
| Mid | ~$0.55 | Seasonal decline continues at its measured rate, competitor adds ~3% to CPM |
| High | ~$0.63 | Steeper seasonal decline, some fade in the launch lift, competitor adds ~6% to CPM |

The three cases share the same starting point and differ in how the two opposing forces net out. That spread, not the mid alone, is the deliverable.

## 4. Assumptions and what drives the spread

- The post-launch plateau is the right baseline, the pre-launch decline is not, because the product change is durable.
- The seasonal decline continues into June rather than reversing.
- The launch-week spend spike is excluded as a one-off.
- The competitor effect is a stated assumption, not derived from the data, since it has not happened yet.

The biggest source of uncertainty is that the **seasonal drag and the launch lift pull in opposite directions**. If the lift fades faster than the season softens, CPC runs toward the high case; if the lift holds and the season is mild, it runs toward the low case. That tension is the width of the band. Widen it further if you expect a stronger competitor push or a weaker product follow-through. This is a fixed-width uncertainty band, not a statistical prediction interval.

## 5. What the range means for the plan

CPC is what a click costs, so the range tells you roughly how much traffic a given June budget buys. At ~$1,000/day held flat, the mid case buys meaningfully fewer clicks than the pre-launch baseline would have implied, because costs are drifting up. Use the range to decide whether to hold spend, scale, or reallocate, and remember that scaling up raises CPC on its own (pricier inventory), so a budget increase is a separate forecast.

## Common mistakes

- Forecasting off the whole 90 days as one trend, which averages the pre-launch decline with the post-launch plateau and lands nowhere real. Forecast off the post-launch level.
- Excluding the May step-up as if it were a promo. It is a durable change, not a bounded event, so it carries forward.
- Leaving the launch-week spend spike in the baseline, which overstates normal spend and traffic.
- Forecasting a flat CPC and ignoring the seasonal softening that continues into June.
- Treating the competitor pressure as a fact in the data instead of a labeled forward assumption.
- Reporting a single number instead of a range, when the whole point is that two forces pull against each other.
