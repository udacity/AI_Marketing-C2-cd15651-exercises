# Stress-Test a Strategy, Surface the Assumptions

Flowline is weighing a growth play, and it's your call whether it's ready. Run the strategy through an adversarial review, surface the assumptions it quietly depends on, and land a defensible position.

Work in Claude Code. The strategy is in [`strategy-brief.md`](strategy-brief.md).

The brief has an obvious first-order story (people who rely on the feature will pay to keep it). The real work is surfacing the second-order effects that story hides — resentment, churn, users leaving for a competitor.

## What to produce

A short document containing:

- Claude's naive evaluation of the strategy (the "is this good?" answer), saved for contrast.
- The adversarial-reviewer output.
- The 3–5 hidden assumptions, ranked by how much damage they'd do if wrong.
- One critique from the adversarial review that you would actually discount, and why.
- A cheap test for the single most dangerous assumption.
- Your revised position in one tight statement: your recommendation, your single deciding reason, and the one condition that would change your call.

## Requirements

- Build a real adversarial-reviewer prompt: assign a skeptical role, and demand the hidden assumptions plus the strongest counter-case. Don't just ask "what are the risks?"
- Rank the assumptions — a flat list isn't the deliverable. The ranking is where your judgment shows.
- Push back on the AI. Its critique is not automatically right; naming what you'd discount, and why, is part of the skill.
- The test for the top risk must be genuinely cheap — something you could run before betting the strategy on it, not "launch it and see."

## Done when

Your one-line revised position could stand up in front of leadership: a clear call, the reason behind it, and the condition that would flip it.
