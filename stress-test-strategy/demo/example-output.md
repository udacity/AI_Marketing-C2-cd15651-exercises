# Demo Output: Turn Claude Into an Adversarial Reviewer

*Illustrative Claude output for the execution-mode reframe: an execution request, then the adversarial reframe, then folding the critique back in. One run; outputs vary.*

**Strategy:** "Offer every free user their first month of Premium free, they'll be hooked enough to keep paying."

## Run 1: execution mode (`Help me craft a plan for executing that tactic`)

> Here's a rollout plan. **Eligibility:** one-time-per-account flag to prevent repeat redemption. **Billing:** collect a payment method up front and auto-convert unless canceled (converts better than card-free trials). **Lifecycle:** a day-by-day touchpoint schedule with reminders before the charge. **Rollout:** pilot a cohort, instrument it, then flip it on for the full base...

*It never asked whether the tactic is a good idea. It took the premise as settled and started building, that's the trap.*

## Run 2: the adversarial reframe

**Prompt:** `Act as a skeptical growth lead who thinks this is flawed. Your north star is incremental paying subscribers. Find the 3-5 assumptions it depends on and would fail on, and the strongest case against.`

> 1. **The barrier is discovery, not fit or price.** If free users have already decided Premium isn't worth it, 30 days of exposure just delays the same "no."
> 2. **Trial usage causes durable preference,** rather than being consumed because it's free and collapsing when the price returns.
> 3. **Redeemers aren't the high-intent users who'd have converted anyway** (adverse selection, you cannibalize organic conversions and call them wins).
> 4. **Auto-converted, coerced payers behave normally,** rather than driving chargebacks, disputes, and "sneaky billing" sentiment that spills onto organic signups.
> 5. **Giving it away doesn't reset expected price,** training future cohorts to wait for the free month.
>
> **Strongest case against:** it's built to look like a success on Day-30 conversion (the metric that gets it funded) while hiding failure on Day-90 incremental net-new, once you strip out cannibalization and post-charge churn.

## Demo beats on top of this

- **Judge, don't obey:** a claim like "this will permanently devalue the brand" is overstated for a time-boxed campaign, discount the framing, keep the point.
- **Close the loop (`What changes would you make?`):** intent-based targeting instead of the whole base; no-card trial; protect existing payers; measure incremental revenue vs. a held-out control; soften the day-30 cliff plus a cancellation survey; kill-switch thresholds. A materially better plan, only because you stopped to attack your own idea before building it.
