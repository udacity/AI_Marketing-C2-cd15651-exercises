# Sample Output — Findings Report

*Actual Claude output — a representative isolated run of the barrier question across 12 persona variants. (The exercise asks students for 100+; this worked example uses 12 to show the method and shape — the pattern holds at scale.) One run; outputs vary.*

**Question:** what would stop you from buying this furniture-grade modern dog bed? · **Method:** 12 variants across 6 archetypes, each run in its own clean isolated context.

## Responses (top barrier per variant)

| # | Archetype | Top barrier |
|---|---|---|
| 1 | urban design | "Looks nice — but is it actually durable, or just marked up?" |
| 2 | urban design | "Will it really match my space, or look out of place in person?" |
| 3 | urban design | "Premium usually means flimsy — will it hold up?" |
| 4 | multi-dog | "Won't survive my chewer" |
| 5 | multi-dog | "Can it actually go in the machine?" |
| 6 | multi-dog | "Durability — I've thrown out too many 'premium' beds" |
| 7 | new puppy | "Too expensive while she's still destroying things" |
| 8 | new puppy | "Puppy will wreck it before it's worth it" |
| 9 | budget | "Not worth the price for a dog bed" |
| 10 | budget | "Price — hard to justify" |
| 11 | senior-dog | "Will the foam flatten / is it supportive enough?" |
| 12 | large-breed | "Will it be big and sturdy enough?" |

## Ranked barriers

| Rank | Barrier | Count | % |
|---|---|---|---|
| 1 | Durability / "pretty but flimsy" | 5 (#1,3,6,11,12) | ~42% |
| 2 | Price / not worth it | 3 (#7,9,10) | ~25% |
| 3 | Won't survive chewing/accidents | 2 (#4,8) | ~17% |
| 4 | Washability | 1 (#5) | ~8% |
| 5 | Won't match space | 1 (#2) | ~8% |

## Barriers by segment

| Barrier | urban design (3) | multi-dog (3) | new puppy (2) | budget (2) | senior-dog (1) | large-breed (1) |
|---|---|---|---|---|---|---|
| Durability / "pretty but flimsy" | **2** | 1 | — | — | **1** | **1** |
| Price / not worth it | — | — | 1 | **2** | — | — |
| Won't survive chewing/accidents | — | 1 | 1 | — | — | — |
| Washability | — | 1 | — | — | — | — |
| Won't match space | 1 | — | — | — | — | — |

Read the rows, not the totals: durability is the top barrier overall but it is **absent among budget and new-puppy owners**, who raise price instead. Washability is a multi-dog concern only. Segment structure is the finding here — the ranked list alone would hide it.

## Signal vs. synthetic consensus

Durability is **genuine signal**: it appears across *different* archetypes in *different words* — design owners frame it as "premium = flimsy," multi-dog owners as "chewing survival," the senior owner as "foam flattening." Varied framing + dissent (design owners barely mention chewing) = a real pattern, not one echoed phrase.

## Calibration disclosure

> Synthetic, directional research. Legitimate claim: *which* barriers to investigate and how they differ by segment. Not legitimate: real prevalence — "42%" is a model artifact, not a measurement. Isolated contexts make each response an independent draw; live customer research is still required before acting.

## Recommendation (directional)

Before launch: (1) **prove durability** — the top, cross-segment barrier; lead with materials, testing, warranty. (2) **justify price** for non-design buyers.
