# Forecast Next Month's CPC

You run paid media for Steep, a direct-to-consumer tea brand. This is a traffic campaign, so the metric you budget against is CPC, your cost per click. You have 90 days of daily data covering March through May, and you need a defensible CPC forecast for next month, June, so the team can plan spend.

Work in Claude. The dataset is [`steep_traffic_90day.csv`](steep_traffic_90day.csv): date, campaign, spend, impressions, CPM, clicks, CTR, and CPC.

**Scope:** the data is campaign-level. It does not include creative-level metrics like engagement rate or hook rate, so don't go looking for those.

## What you already know

Three things about this period, which you'll reconcile against what the data shows:

1. **Seasonal demand.** The campaign runs from late winter into early summer, and tea sells less as the weather warms. Demand softened across the stretch.
2. **A new product launch.** Steep launched a new product in early May, and it brought performance back up. The product is staying in the line. The launch came with a short burst of extra spend that was a one-off push, not the normal budget.
3. **A competitor move (not in the data).** A well-known coffee brand is launching its own tea line next month. You expect the added competition to push your CPMs up for a while.

## What to produce

- A 30-day CPC forecast for June as a range: low, mid, and high, with the reasoning and the calculation behind each case.
- How you treated each pattern you found (carry it forward, exclude it, or adjust for it) and why.
- The assumptions behind the forecast and what drives the width of the range.
- A short read on what the range means for next month's plan.

## Requirements

- Have Claude describe the patterns in the data before you forecast. Find them first, then line them up against the three facts above.
- Decide what carries into June. Next month is deeper into summer, so ask of each pattern whether it will still be true.
- The seasonal decline and the product-launch lift pull in opposite directions. Say how they net out. That tension is the real work here.
- Give ranges, not point estimates, and state the assumptions behind each.
- The competitor pressure is not in the data. If you account for it, label it a stated assumption, not a data-derived result.

## Done when

Your forecast gives a defensible CPC range for June, shows how each pattern was handled and why, and a stakeholder could plan next month's spend from it without redoing your work.
