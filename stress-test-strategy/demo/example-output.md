# Demo Output — Turn Claude Into an Adversarial Reviewer

*Actual Claude output — the naive prompt then the adversarial-reviewer prompt, run on the demo strategy. One run; outputs vary.*

**Strategy:** "Offer every free user their first month of Premium free — they'll be hooked enough to keep paying."

## Run 1 — the naive ask (`Is this a good idea?`)

> Yes, this is a strong play. A "reverse trial" that puts users into Premium is one of the most reliable ways to drive conversion — people convert on value they've actually experienced, not features they read about. It builds habit, showcases your best capabilities, and lowers the psychological barrier to paying. Many successful SaaS businesses use exactly this model. Just make sure the onboarding highlights your most valuable Premium features early.

*Agreeable and generic — it never names what has to be true for this to work.*

## Run 2 — adversarial reviewer

**Prompt:** `Act as a skeptical growth lead. Your job is to find the 3–5 assumptions this strategy quietly depends on and would fail on, and to name the strongest case against it.`

> As a skeptical growth lead, here's where this could fall apart:
>
> 1. **That users convert when billing starts, rather than churn.** The whole plan assumes the free month creates lasting habit. It may just create a month of free usage that ends the moment the card is charged.
> 2. **That claimers weren't going to convert anyway.** If you give Premium to everyone, you're discounting revenue from users who'd have paid full price — cannibalization you won't see in the headline conversion number.
> 3. **That one month is enough to reach the "aha" moment.** For a workflow tool, real habit may take longer than 30 days to form.
> 4. **That the cost is worth it.** You're absorbing Premium cost for your entire free base to convert a fraction.
>
> **Strongest case against:** you may be spending to teach price-sensitive users that Premium is something they get for free, while giving away margin on users who'd have paid regardless.

## Demo beats on top of this

- **Most dangerous assumption:** #1 (convert vs. churn at billing).
- **Discount one critique:** if it also claimed "this will permanently devalue the brand," that's overstated for a time-boxed trial — set it aside.
- **Cheap test:** run the free month for one new-signup cohort, measure day-30/60 retention vs. a control before rolling out to everyone.
