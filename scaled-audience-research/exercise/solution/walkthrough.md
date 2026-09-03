# Solution — Run It at Scale, Then Find the Edge

*Worked solution — one strong example. The barrier percentages below are illustrative of a plausible 24–30 run; a student's will differ. What matters: enforced independence with evidence (not just a claim), a roster-bias audit, a real signal-vs-consensus check, an honest calibration disclosure, and a surface note.*

## The workflow (how independence was enforced)

1. **Archetypes + attributes.** Define 5–6 archetypes (design-focused urban owner, practical multi-dog owner, new puppy owner, budget-conscious owner, senior-dog owner, large-breed owner) and vary age, location, home type, price sensitivity, and one or two personality traits.
2. **Generate variants.** Use the variant-generation prompt to produce 24–30 distinct variants across the archetypes.
3. **Isolated runs.** In Claude on the agent surface (Cowork), run each variant via a subagent in its own clean context (one subagent call per persona, no shared history) asking the single barrier question: *"What would stop you from buying this furniture-grade modern dog bed?"*
4. **Collect.** Write each response to a common structured format (variant id, archetype, top barrier, verbatim) into one file, then aggregate.

Independence is the point: if all 24–30 ran in one conversation, later personas would anchor on earlier ones and the "sample" would collapse into one correlated voice.

**Evidence of independence (not just the claim).** Claude's own write-up and progress checklist will say "independent" whether or not it was — both are prose it generated. The check is the system-reported count: how many subagent runs actually fired? In Cowork, each subagent spawn is a discrete tool call visible in the conversation; count them and compare to your variant count. 24–30 variants → 24–30 subagent calls. A mismatch means some personas ran in shared context. Document the count in your report.

## Aggregated barriers (illustrative, n=30)

| Rank | Barrier | % raising it | Notes |
|---|---|---|---|
| 1 | Durability / "pretty but flimsy" | ~42% | top overall, but raised in 4 of 6 archetypes — not by budget or new-puppy owners |
| 2 | Price / not worth it for a dog bed | ~25% | budget + puppy owners |
| 3 | Won't survive chewing / accidents | ~17% | multi-dog and puppy owners |
| 4 | Washability | ~8% | multi-dog owners |
| 5 | Won't match my space | ~8% | design owners |

The by-segment breakdown is the other half of the deliverable — see the **Barriers by segment** cross-tab in [`example-output.md`](example-output.md), which shows the same barriers split by archetype. Chart it as a stacked bar of barriers × archetype. The segment view is where the actionable finding lives: a barrier that ranks first overall but is absent in two segments is a targeting instruction, not a universal one.

## Signal vs. synthetic consensus

The **durability doubt (#1) is genuine signal**: it shows up across *different* archetypes, in *varied* wording, and coexists with dissent (design owners care less about chewing, more about "premium = flimsy?"). That variation is what real signal looks like.

A **red flag to watch:** if 90%+ had returned the same barrier in near-identical phrasing, that's manufactured consensus (an artifact of the model, not the audience) — here the spread and the segment differences argue it's real.

## Roster-bias audit

Before reading the barrier rankings as market signal, read them against the roster that produced them. The ~30-variant roster breaks as: design-focused (~4–5), multi-dog (~4–5), new-puppy (~4–5), budget-conscious (~4–5), senior-dog (~4–5), large-breed (~4–5) — roughly equal.

**Roster-decided:** Price (#2, ~25%) is close to what the seed predicts — ~33% of the roster is price-sensitive archetypes (new-puppy + budget, 2 of the 6). A finding that tracks the roster proportion is informative, but it's partly a fact about who you asked, not just about the market.

**Response-decided:** Durability (#1, ~42%) appears across archetypes that weren't seeded as durability-focused. That cross-archetype pattern is less likely to be a seed artifact and more likely to reflect something real about the product category.

Implication: Durability is the stronger signal. Price warrants validation against a more balanced roster before treating it as equally actionable.

## Calibration disclosure

> This is synthetic, directional research. It can legitimately claim *which barriers are worth investigating* and *how they differ by segment*. It **cannot** claim real-world prevalence — "42%" is a model artifact, not a market measurement. Independent contexts make each response a genuine separate draw (not an echo), which is why the spread is meaningful; but real customer research (surveys, interviews, a live pre-order test) is still needed before acting at scale.

## Recommendation

Two barriers to address before launch, **labeled directional**: (1) **prove durability** — the top, cross-segment concern; lead with materials/warranty/testing. (2) **justify price** for non-design buyers. Validate both with real customers before committing.

## Surface note

At this exercise's n (24–30 variants) this workflow runs cleanly on the agent surface. At 100+ variants, two strains appear:

- **Cost and partial failures.** 100+ subagent calls in one Cowork session adds up, and has no resume point — a mid-run failure restarts the whole batch.
- **Aggregation becomes estimated.** Past ~40 responses, collating verbatim answers into barrier categories feels like re-summarizing rather than counting. One human audit pass over the model's categorisation is still worth it.

**Move it when:** you need to run this on a weekly cadence, or n is large enough that auditability matters and estimated counts aren't enough. The deciding factor is frequency and auditability requirement, not whether the tool *can* run at scale. For a one-off pre-launch read: stay on this surface.

## Common mistakes

- Running variants in one shared context (anchoring) — kills independence.
- Claiming independence without checking the system-reported run count — Claude's own summary will say "independent" either way.
- Defining only 3 persona archetypes and cycling through them — each subagent runs independently, but if the *personas* repeat, you're sampling the same 3 opinions in isolation, not spanning your audience. Generate 24–30 genuinely distinct variants across your archetypes.
- Reporting the headline % as if it were survey data (no calibration disclosure).
- Only flagging individual confabulations, never checking aggregate signal vs. consensus.
- Skipping the roster-bias audit — if your archetypes skew price-sensitive, the price finding tells you about your roster, not the market.
- No surface note — "it worked" is not an answer to where the surface starts to strain.
