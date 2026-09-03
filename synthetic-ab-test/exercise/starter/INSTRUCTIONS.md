# Run the Test, Deliver the Recommendation

Barkwell has three creative directions for its furniture-grade modern bed line and needs a defensible pick. Run a full A/B/C test across a provided 3-persona panel and produce a ranked recommendation with confidence and stated limits.

Work in Claude Code. Use:

- [`persona-panel.md`](persona-panel.md) — the three provided personas.
- [`scoring-prompt.md`](scoring-prompt.md) — score each direction, one persona at a time.
- [`aggregation-prompt.md`](aggregation-prompt.md) — aggregate the scores into a ranked recommendation.

**The three directions:**
- **A** — a design-magazine aesthetic angle.
- **B** — a "your dog deserves nice things too" indulgence angle.
- **C** — a "finally, a dog bed you won't hide when guests come over" honesty angle.

## What to produce

- All three directions scored by each of the three personas on the fixed dimensions.
- An aggregation table (totals by concept and by persona).
- The winner, plus any concept that split the panel (strong for one persona, weak for another).
- A confidence level — high / medium / low — with an explicit basis.
- The ranked recommendation with at least three stated limits of the test.
- A next step: the one concept you'd advance to real-world validation, and what specifically you'd test with actual customers.

## Requirements

- Run each persona in a **fresh conversation** so earlier scores don't anchor later ones.
- The confidence level must have a stated basis (spread between concepts, agreement across personas) — not a vibe.
- Call out any concept whose average hides a split panel — strong for one persona, weak for another. A concept like that is a targeted play, not a safe default, and the average alone will not tell you.
- Treat this as a first check that narrows the field, not the final call. The next-step validation is part of the deliverable, not an afterthought.

## Done when

You have a ranked recommendation a stakeholder could act on: a winner, a defensible confidence level, the panel splits, the limits, and a concrete plan to validate the front-runner for real.
