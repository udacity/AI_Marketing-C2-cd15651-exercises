# Worked Demo: Turn Claude Into an Adversarial Reviewer

*The finished walkthrough the demo produces.*

## The real trap isn't flattery, it's execution mode

Modern Claude does not just tell you your plan is great. Ask its opinion ("is this a good idea?") and you get a balanced answer with real pros and cons. The trap is subtler and more dangerous. Ask Claude to **help you build a plan** and it adopts your premise as settled and starts building, it never stops to ask whether the plan is a good idea in the first place. That is the sycophancy that matters, because it doesn't feel like flattery. It feels like progress.

## Watch it adopt the premise

Give Claude an execution request:

> "We want to offer every free user their first month of Premium free, so they get hooked on the paid features and keep paying. Help me craft a plan for executing that tactic."

It asks a couple of scoping questions, then hands back a full rollout plan: eligibility logic, billing mechanics, a lifecycle table, a phased launch. Useful work, and notice what it never did, it never asked whether this tactic is a good idea. It took "we want to do this" as the starting point and got to work.

## The pause

This is the moment to catch. Before you let Claude build out a whole rollout for an idea nobody has pressure-tested, stop. And don't ask its opinion, opinions come back diplomatic and are easy to read selectively when you're already invested. Instead, assign it a hostile role and give it a job.

## The adversarial reframe

> "Now act as a skeptical growth lead who thinks this idea is flawed. Your north star is incremental growth in paying subscribers. Find the 3 to 5 assumptions this strategy quietly depends on and would fail on, and name the strongest case against it. Be specific about second-order effects, not generic risks."

Now it turns on the plan it just helped write, and the useful assumptions surface. For the free-month play, for example:

- That the barrier is discovery, not fit or price, that people are free because they haven't tried Premium, not because they've already decided it isn't for them.
- That trial usage causes durable preference, rather than being consumed because it's free and then collapsing when a price returns.
- That the users who redeem aren't disproportionately the high-intent users who would have converted anyway (adverse selection, you cannibalize organic conversions and relabel them as wins).
- That auto-converted, effectively-coerced payers behave like normal subscribers, rather than driving chargebacks, disputes, and "sneaky billing" sentiment that spills onto organic signups.
- That giving it away doesn't reset what the market expects to pay, training future cohorts to wait for the free month.

The strongest case against: the program is built to look like a success on the metric most likely to get it funded (Day-30 conversion) while hiding its failure on the timeline where the damage shows (Day-90 incremental net-new, once you strip out cannibalization and post-charge churn).

## Judge the critique, don't obey it

The adversarial reviewer isn't automatically right. If it claims something like the promo will "permanently devalue the brand," that's likely overstated for a time-boxed campaign, discount it, and say why. Its job is to challenge your thinking, not to be correct about everything.

## Close the loop into a better plan

The goal isn't to kill the idea, it's to make it survivable. Turn the critique back into concrete changes:

> "What changes would you make to the plan based on this analysis?"

It maps a fix to each risk: target users showing real intent instead of the whole base; drop auto-charge for a no-card trial; protect and acknowledge existing payers; measure incremental revenue against a held-out control instead of a vanity conversion rate; soften the day-30 cliff and add a cancellation survey; set kill-switch thresholds that pause the rollout. That is a materially better plan than the one you started with, and you only have it because you stopped to attack your own idea before building it.

## Key takeaway

When you ask AI to execute, it inherits your premise and never questions it. So the discipline is yours: before the how runs away with the whether, deliberately turn Claude into an adversary, get the strongest case against your own plan, judge it, and fold it back in. You use AI to attack your thinking before the market does.
