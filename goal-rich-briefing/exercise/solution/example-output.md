# Sample Output: One Goal, Four Prompts

*Illustrative Claude output, the same abandoned-cart email written four ways. One run; outputs vary. Emails trimmed for readability.*

## Email 1: over-prescribed prompt

> **Still deciding between free and Premium?** Premium members finish their to-do lists 20% faster thanks to workflow shortcuts, cross-device sync, and unlimited projects, all waiting in your cart. **Your 20% launch discount holds for the next [COUNTDOWN 23:59:59]**, so lock it in before it resets to full price. Complete your upgrade now and start moving through your projects faster today.
> *P.S. Still have questions? Just reply, we're happy to help.*

*The tell: to satisfy the rigid rules, it invented a **20% launch discount and a countdown** nobody authorized, which contradicts Flowline's no-discount policy. Rules without direction produced a risky guess.*

## Email 2: under-specified prompt

> **Subject: You left Premium in your cart.** Looks like you were checking out Flowline Premium and got pulled away. No worries, your cart's still there. Here's what's waiting: sync across every device, unlimited projects, and workflow shortcuts. [Finish upgrading to Premium →] *P.S. Your cart will hold for 48 hours.*

*Competent but generic. It had to guess the trigger and invented a "48-hour hold." It even flagged its own assumption ("let me know if it's a paywall-hit instead").*

## Email 3: vague prompt

> **Subject: Still thinking it over?** Looks like you started upgrading and didn't quite finish, no worries. Here's what you'd unlock: [benefits]. If something got in the way, hit reply. Otherwise, picking back up takes about 30 seconds: [Finish upgrading →]

*Pleasant but aimless, it offered subject-line options and to draft a follow-up sequence. "Reconnect" gave it no single goal to drive.*

## Email 4: goal-rich brief

> **Subject: Your Premium cart is still here.** Hi [First Name], looks like you got right up to the finish line on annual Premium and got pulled away, your cart's still ready when you are. Annual works out to about $8 a month, a third less than monthly, and it's cancel-anytime with a 14-day money-back guarantee, so there's no risk in finishing now. [Finish your purchase] If something didn't look right or you had a question about the plan, just reply, happy to help. The Flowline Team

*Speaks to the real hesitation (the annual commitment), reassures with an honest safety net instead of an invented discount, one CTA. Shorter than Email 1, and the only one that isn't guessing.*

## Comparison

The goal-rich email wins because every line targets the actual moment: it reassures on the annual commitment, cites the real 33% saving and the money-back guarantee, and asks for one thing. The weak three each failed in their own way, an invented discount, guessed details, or no ask, because the prompt left those decisions to the model instead of making them.
