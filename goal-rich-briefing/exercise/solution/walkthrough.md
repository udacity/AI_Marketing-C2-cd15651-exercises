# Solution: One Goal, Four Prompts

*Worked solution, one strong example. Outputs vary; what matters is a correct diagnosis of each weak prompt, a goal-rich brief that carries real decisions, and a concrete comparison of the four.*

## The setup

Same task four times: an abandoned-cart email for a user who reached checkout for annual Premium and left. Holding the task constant means the only variable is the prompt, so the four outputs isolate what prompt quality actually buys you.

An honest note up front: current models are good enough that even a weak prompt produces a *competent-looking* email. So the lesson isn't "weak prompt, bad email." It's that **weak prompts make the model guess, and its guesses can be wrong or off-brand**, while a goal-rich brief makes it execute your intent.

## Diagnosing the three weak prompts

- **Prompt 1 is over-prescribed.** It's all mechanics (exactly four sentences, a countdown, a mandatory question, a P.S.) and no direction. Run it and the model doesn't just sound robotic, it **invents a "20% launch discount" and a countdown that were never authorized**, to satisfy the "countdown timer" rule. That's the teachable failure: an over-prescribed prompt forced a guess that contradicts Flowline's no-discount policy and could train customers to wait for discounts. Fix: cut the arbitrary rules and put real direction in their place.
- **Prompt 2 is under-specified.** "Write an abandoned-cart email for Flowline" gives the model nothing about who this is, what they abandoned, or why they'd care. It produces a reasonable generic cart email, but it has to guess the trigger and invents details (a "48-hour hold"). Fix: add the missing facts.
- **Prompt 3 is vague.** "Write something to reconnect with them" has a vibe but no goal. "Reconnect" isn't an ask, so the output wanders (subject-line options, offers to draft a follow-up sequence) and never drives the one action. Fix: give it a real goal, completing the purchase.

## The goal-rich brief

Front-load the five decisions you already own, using the real Flowline facts:

> **Audience:** a user who reached checkout for annual Premium and left without completing.
> **Goal:** get them back to finish the annual Premium purchase.
> **Context:** they were one step from paying, so they already want it; the usual hesitation is the annual commitment, even though annual ($96/year, about $8/month) is ~33% cheaper than monthly. This is a reassuring nudge, not a fresh pitch.
> **Constraints:** short and warm; one clear CTA straight back to checkout; no countdown gimmick; **no discount** (we don't discount), reassure with cancel-anytime and the 14-day money-back guarantee instead.
> **Success:** they click back to checkout and complete.

This produces a tight, on-brief email that reassures on the exact hesitation (the annual commitment), offers a real safety net (cancel-anytime, money-back) instead of an invented discount, and drives one action.

## The comparison (the payoff)

Put the four side by side and name the difference concretely:

- **Over-prescribed:** invented a discount that violates policy, robotic, gimmicky. Actively risky.
- **Under-specified:** competent but generic; guessed the trigger and a hold time.
- **Vague:** pleasant but aimless; never makes the ask.
- **Goal-rich:** speaks to the real hesitation, offers an honest reassurance, one CTA, no invented anything.

The goal-rich email wins not because it's longer, it's often shorter, but because every line was aimed at the real moment, and it replaced the model's guesses with your decisions.

## Common mistakes

- Treating "the weak output looks fine" as proof the prompt was fine, missing the guesses baked into it (the invented discount is the clearest tell).
- Diagnosing every weak prompt as "needs more detail." The over-prescribed one needs *less*.
- A goal-rich brief full of placeholders ("Audience: our users") instead of real decisions.
- A comparison that says "the last one is better" without naming the specific decision that made it better.
