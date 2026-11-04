# Worked Demo — Slicing LTV to Find the Real Driver

*The finished walkthrough the demo produces. Ad platforms default to acquiring customers as cheaply as possible, which often means buying the lowest-value users. To use value-based bidding effectively, marketers need to tell the platform exactly how much different types of customers are actually worth.*

In this demo, we use Claude to find what truly drives lifetime value for Steep. The dataset is [`steep_cohorts.csv`](steep_cohorts.csv): about 4,800 customer records with geography, monthly fee, active or churned status, and whether each customer paid full price or got a discount.

## How the baseline is set up

We start by establishing a baseline metric. The chat assistant calculates a blended lifetime value using a simple formula: Average observed tenure multiplied by the average monthly fee. While this is a useful simplification, it undervalues customers who are still active because their final tenure is not yet known. Still, it provides a starting point before we slice the data to see how different segments perform against that $81.24 average.

A request like this works well to establish the baseline:

> Using the attached customer file, compute a single blended average lifetime value as the average observed tenure in months multiplied by the average monthly fee, across all customers. Return only that one LTV number and the two averages behind it. Do not segment by anything, do not adjust for customers still active, and do not add any caveats or commentary.

## How to spot a confound

Next, we ask the AI tool to cut the data by different customer attributes to see what actually drives value. A naive cut by geography makes India look like a terrible market, returning a lifetime value of just $69.02 compared to Canada's $90.33. However, comparing segments side by side reveals a confound. When we cross-reference geography with acquisition type, we find that 80.6% of Indian customers buy at a discount, and discount buyers have a significantly lower lifetime value across the board.

| Geography | Raw LTV | % on discount | Full-price LTV |
| --- | --- | --- | --- |
| CA | $90.33 | 25.2% | $100.32 |
| US | $85.58 | 39.8% | $102.80 |
| UK | $82.00 | 46.9% | $100.49 |
| IN | $69.02 | 80.6% | $102.84 |

As the table shows, a full-price customer in India is worth about the same as a full-price customer in Canada, the US or the UK (around $100 to $103). The geography does not drive the value; the acquisition type does.

## What the result tells you

Finally, we use an open prompt asking Claude to look holistically at the trends. This confirms that acquisition type dominates everything else, with full-price customers worth roughly 66% more than discount buyers ($101.60 vs. $61.20). This judgment supports value-based bidding: Instead of feeding the ad platform a blanket target, we can instruct it to value full-price sign-ups higher and discount sign-ups lower in the bids.

To check for broader patterns, we hand over the analysis:

> Look holistically at the customer data and tell me what trends you see around the best and worst LTV by user profile

**Takeaway:** Instead of just applying a blanket $80 blended LTV, we can get much more nuanced.

**Try it:** Attach your own customer data and ask the chat assistant to cross-reference your lowest-value segment against acquisition channels to check for confounds.
