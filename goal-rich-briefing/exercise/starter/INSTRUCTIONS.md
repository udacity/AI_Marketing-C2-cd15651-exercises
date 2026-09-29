# One Goal, Four Prompts

You run lifecycle and conversion messaging for **Flowline**, a freemium productivity app. You're going to write the *same* email four different ways and put the results side by side, so the only thing that varies is the quality of the prompt.

The task, every time: an **abandoned-cart email** to a user who reached checkout for annual Premium and left without completing the purchase. You've been handed three deliberately weak prompts for it, each broken in a different way. Run each, diagnose the failure, then write your own goal-rich brief for the same email and compare all four.

Work in Claude. The three weak prompts and the product facts are in [`starter-prompts.md`](starter-prompts.md).

## The three failure modes

- **Over-prescribed**, stuffed with rigid rules but no real direction. The fix is usually to *cut*.
- **Under-specified**, missing the key facts.
- **Vague**, no real goal at all.

## What to produce

A single document containing:

- The three weak prompts, each run as-is, with the failure type you diagnosed for it.
- Your **goal-rich brief** for the same email, built on the five-element scaffold: **Audience, Goal, Context, Constraints, Success criteria** (use the real Flowline facts).
- All four outputs placed next to each other.
- A short comparison: which output is most likely to get the abandoner back to complete the purchase, and what specifically the weaker three were missing.

## Requirements

- **Diagnose before you rewrite.** The fix follows from the failure type, and it isn't always "add more." The over-prescribed prompt needs its arbitrary mechanics cut and real direction put in their place.
- **Watch for guessing.** Because current models fill gaps competently, a weak prompt often produces a *decent-looking* email built on guesses, some of them wrong or off-brand. (Notice whether a prompt makes the model invent things you never authorized, like a discount, when Flowline doesn't discount.) The goal-rich brief's job is to replace those guesses with your actual intent.
- **Every brief element must carry a real decision,** not a placeholder. "Audience: our users" is not a decision; "a user who reached checkout for annual Premium and left" is.
- **Make the comparison concrete.** Name the specific thing that separates the goal-rich output from the weak three, not just "it's better."

## Done when

You can point to the four outputs and explain why the goal-rich one wins, and your diagnosis of how each weak prompt failed holds up, rather than just a feeling that its output was worse.
