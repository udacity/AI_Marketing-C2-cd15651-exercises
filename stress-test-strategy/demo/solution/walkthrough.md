# Worked Demo — Turn Claude Into an Adversarial Reviewer

*The real content: the finished walkthrough the demo produces.*

## The strategy under test

> "Offer every free user their first month of Premium free — let them live in the paid tier for a month and they'll be hooked enough to keep paying."

It sounds obviously right — which is exactly why it needs stress-testing.

## The naive ask

Prompt Claude with *"Is this a good idea?"* The answer comes back agreeable and largely useless: it validates the plan and lists generic upsides. Asking the model what it thinks gets you flattery.

## The adversarial reframe

Reassign the role:

> "You are a skeptical growth lead. Your job is to find the 3–5 assumptions this strategy quietly depends on and would fail on, and to name the strongest case against it."

Now the useful assumptions surface:

- That a free month creates a *lasting habit* rather than a free ride that ends the moment billing starts.
- That the people who claim the free month were not already about to convert — otherwise you're cannibalizing revenue you'd have earned anyway.
- That one month is long enough to reach the product's aha moment.

## Pick the most dangerous assumption

The sharpest risk: *the strategy assumes users convert when billing kicks in, rather than churning the instant the free month ends.* If that's wrong, the whole play loses money.

## Judge the critique itself

The adversarial reviewer isn't automatically right. For instance, if it claims the promo will "devalue the brand permanently" *(illustrative — not from source)*, that's likely overstated for a time-boxed trial — discount it, and say why. The reviewer's job is to challenge your thinking, not to be right about everything.

## Turn it into a cheap test

Ask Claude how to test the most dangerous assumption before committing: e.g., run the free month for a *single cohort* and measure retention at day 30–60 against a control, rather than rolling it out to everyone. *(Illustrative test design — not from source; swap for your own.)*

## Key takeaway

AI's default mode is agreement. The value is in the adversarial reframe — you use it to attack your own thinking before the market does, and the payoff is the cheap test that saves the expensive mistake.
