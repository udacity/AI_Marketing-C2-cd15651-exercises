# Run a Real Red Team on High-Stakes Copy

You're about to send Flowline's biggest email of the quarter, a launch announcement for a new AI feature, to your whole list. Use AI to write it, then run a genuine adversarial review on it and turn what you find into a stronger version. The skill here isn't the writing (AI will do that happily), it's conducting the red team well.

Work in Claude. No starter files, everything is in your prompts.

## What to produce

- **V1:** the launch email, written by Claude from your brief.
- **The red team:** an adversarial critique you elicited by assigning a persona, stating a goal, and explicitly asking Claude to attack the copy, name what isn't working and why, and be specific about second-order effects (trust, refunds, unsubscribes), plus how to mitigate each.
- **V2:** a stronger version that fixes the issues the red team surfaced while keeping what worked.
- **A short change memo:** why V2 is better than V1, and how the adversarial review produced each improvement.

## Requirements

- **Have Claude write the copy first.** Notice that when you ask it to write, it runs with your angle and never questions it. That's why the review is on you.
- **Set the red team up deliberately.** A good adversarial prompt has three parts: a *persona* for Claude to inhabit (e.g., a skeptical brand or lifecycle lead), a *goal* it optimizes for (e.g., durable trust and paid retention, not click-through), and an *explicit instruction* to red-team the work, name each weakness and why it's a risk, and propose a mitigation. "Any feedback?" is not a red team.
- **Push for second-order effects,** not line edits. The valuable critiques are about what happens after the click: broken-promise churn, refund spikes, deliverability, brand trust.
- **Turn the critique into V2,** don't just collect it. V2 has to visibly address the specific risks the review raised.
- **Show your work.** The change memo is what proves the review did something, each change tied back to the risk it fixes.

## Done when

You have a V1, a red team you set up with a clear persona and goal, a V2 that fixes the surfaced risks, and a short memo that a lead could skim to see why V2 is the version to send and how the adversarial review got you there.
