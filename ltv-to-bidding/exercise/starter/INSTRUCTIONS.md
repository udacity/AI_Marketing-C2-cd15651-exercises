# Find What Drives LTV and Make One Spend Change

It is time to find out what actually drives customer lifetime value so you can bid smarter.

## What you're given

You are working with Steep, a direct-to-consumer tea brand. The goal is to move toward value-based bidding. This approach tells ad platforms how much a customer is worth ("here is how much I can spend to acquire a user") instead of simply asking them to get new customers as cheaply as possible. To do that, you need to look past the blended LTV, which is just the average value across all customers. You must find out what actually makes one customer more valuable than another.

The dataset is [`steep_cohorts_exercise.csv`](steep_cohorts_exercise.csv). This file contains 4,800 customer records to help you analyze what drives value, including acquisition channels, geography, income bands, plan types, and monthly fees.

For this analysis, you will use a simplified LTV calculation: Average observed tenure multiplied by the average monthly fee. Keep in mind that this is a simplification that undervalues customers who are still active, but it provides a clear enough baseline to compare different segments. You will also need to watch out for a confound: An attribute that appears to drive lifetime value but is actually explained away by a different underlying factor.

## Your task

1. Hand the dataset to Claude and ask it to segment the customers to find the highest and lowest lifetime value groups.
2. Ask the AI tool to identify the single customer attribute that drives lifetime value the most.
3. Have the chat assistant check for confounds to find one attribute that looks like a driver but is actually explained by something else.
4. Review Claude's findings and decide on one specific change to how you will spend your acquisition budget.

## Done when

- You have isolated the true driver of lifetime value rather than a demographic distraction.
- You have translated the segment analysis into a clear business decision.
- The finished work is a short recommendation answering the four questions and ending with one specific spend change.
