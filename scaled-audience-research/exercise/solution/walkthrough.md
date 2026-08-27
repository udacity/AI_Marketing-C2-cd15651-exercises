# Solution — Build the Workflow, Find the Barriers

*Worked solution — one strong example. The barrier percentages below are illustrative of a plausible 100+ run; a student's will differ. What matters: enforced independence, a real signal-vs-consensus check, and an honest calibration disclosure.*

## The workflow (how independence was enforced)

1. **Archetypes + attributes.** Define 3–4 archetypes (design-focused urban owner, practical multi-dog owner, new puppy owner, budget-conscious owner) and vary age, location, home type, price sensitivity, and one or two personality traits.
2. **Generate variants.** Use the variant-generation prompt to produce 120 distinct variants across the archetypes.
3. **Isolated runs.** In Claude Code, run each variant **in its own clean context** (one call per persona, no shared history) asking the single barrier question: *"What would stop you from buying this furniture-grade modern dog bed?"*
4. **Collect.** Write each response to a common structured format (variant id, archetype, top barrier, verbatim) into one file, then aggregate.

Independence is the point: if all 120 ran in one conversation, later personas would anchor on earlier ones and the "sample" would collapse into one correlated voice.

## Aggregated barriers (illustrative, n=120)

| Rank | Barrier | % raising it | Notes |
|---|---|---|---|
| 1 | "Looks nice but is it actually durable?" | ~38% | strongest across every archetype |
| 2 | Price / not worth it for a dog bed | ~29% | concentrated in budget + puppy owners |
| 3 | Won't survive chewing / accidents | ~21% | multi-dog and puppy owners |
| 4 | Won't match my space after all | ~7% | design owners only |
| 5 | Other / no barrier | ~5% | — |

Chart/table of the full breakdown by segment would accompany this (bar chart of barriers × archetype).

## Signal vs. synthetic consensus

The **durability doubt (#1) is genuine signal**: it shows up across *different* archetypes, in *varied* wording, and coexists with dissent (design owners care less about chewing, more about "premium = flimsy?"). That variation is what real signal looks like.

A **red flag to watch:** if 90%+ had returned the same barrier in near-identical phrasing, that's manufactured consensus (an artifact of the model, not the audience) — here the spread and the segment differences argue it's real.

## Calibration disclosure

> This is synthetic, directional research. It can legitimately claim *which barriers are worth investigating* and *how they differ by segment*. It **cannot** claim real-world prevalence — "38%" is a model artifact, not a market measurement. Independent contexts make each response a genuine separate draw (not an echo), which is why the spread is meaningful; but real customer research (surveys, interviews, a live pre-order test) is still needed before acting at scale.

## Recommendation

Two barriers to address before launch, **labeled directional**: (1) **prove durability** — the top, cross-segment concern; lead with materials/warranty/testing. (2) **justify price** for non-design buyers. Validate both with real customers before committing.

## Common mistakes

- Running variants in one shared context (anchoring) — kills independence.
- Reusing 3 personas 40 times instead of generating 100+ distinct variants.
- Reporting the headline % as if it were survey data (no calibration disclosure).
- Only flagging individual confabulations, never checking aggregate signal vs. consensus.
