# Sample Output — Findings Report

*Actual Claude output — a representative isolated run of the barrier question across 12 persona variants. (The exercise asks students for 24–30; this worked example uses 12 to show the method and shape — the pattern holds at scale.) One run; outputs vary.*

**Question:** what would stop you from buying this furniture-grade modern dog bed? · **Method:** 12 variants across 6 archetypes, each run in its own clean isolated context.

**Independence check:** 12 subagent calls fired (count confirmed from the Cowork conversation history — each persona spawn is a discrete tool call). Matches the 12-variant roster. Claude's own write-up said "independent" regardless; the system count is the fact.

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

### Codebook (how responses were coded)

Aggregation is a judgement call, so the rules go in writing before the counting. The consequential one here is durability vs. chewing — merge them and durability jumps to 58%, which changes the headline.

| Category | Includes | Excludes |
|---|---|---|
| **Durability / "pretty but flimsy"** | doubts about build quality, longevity, foam flattening, "premium = marked up not well made" | destruction by a specific dog |
| **Won't survive chewing / accidents** | a named chewer or puppy destroying it; house-training accidents | general build-quality doubt |
| **Price / not worth it** | cost objection with no quality claim attached | "not worth it *because* it'll break" → durability |
| **Washability** | machine-washable, cleaning practicality | — |
| **Won't match my space** | aesthetic or fit-with-decor doubt | — |

**Kept separate on purpose:** the two get different marketing responses. Durability doubt is answered with materials, testing, and warranty. Chewing concern is answered with a chew-resistant SKU or an honest "not for heavy chewers" disclosure. Merging them would produce one 58% barrier you can't act on with a single message.

## Signal vs. synthetic consensus

Durability is **genuine signal**: it appears across *different* archetypes in *different words* — design owners frame it as "premium = flimsy," multi-dog owners as "chewing survival," the senior owner as "foam flattening." Varied framing + dissent (design owners barely mention chewing) = a real pattern, not one echoed phrase.

## Roster-bias audit

Before reading the barrier rankings as market signal, read them against the roster that produced them.

| Archetype | n | Price-sensitive? | Durability-sensitive? |
|---|---|---|---|
| Urban design | 3 | No | Yes (premium = flimsy framing) |
| Multi-dog | 3 | No | Yes (chewing/washing survival) |
| New puppy | 2 | Yes | Partially |
| Budget | 2 | Yes | No |
| Senior-dog | 1 | No | Yes (support/foam) |
| Large-breed | 1 | No | Yes (size/sturdiness) |

**Roster-decided findings:** Price (#2 barrier, ~25%) is close to what the seed predicts — 4 of 12 variants (33%) are price-sensitive archetypes. "Price is a top barrier" is partly a fact about this roster, not just about the market.

**Response-decided findings:** Durability (#1, ~42%) appears across archetypes that weren't seeded as durability-focused — budget and new-puppy owners, who were seeded price-sensitive, still did not raise it. That cross-archetype pattern is less likely to be a seed artifact.

Implication: Durability is the stronger signal. Price should be validated against a more balanced roster before treating it as equally actionable.

## Calibration disclosure

> Synthetic, directional research. Legitimate claim: *which* barriers to investigate and how they differ by segment. Not legitimate: real prevalence — "42%" is a model artifact, not a measurement. Isolated contexts make each response an independent draw; live customer research is still required before acting.

## Recommendation (directional)

Before launch: (1) **prove durability** — the top, cross-segment barrier; lead with materials, testing, warranty. (2) **justify price** for non-design buyers.

## Surface note

At 12 variants this workflow ran cleanly: each subagent fired, costs were modest, and aggregation was a straight count. At 100+ variants, two strains appear:

- **Cost and partial failures.** 100+ subagent calls in a single Cowork session is expensive, and if one call fails mid-run there is no resume point — you start the batch over. Manageable for a one-off research sprint; painful if this is a recurring workflow.
- **Aggregation becomes estimated.** Past ~30–40 responses, collating verbatim answers into barrier categories starts feeling like re-summarizing rather than counting. The model will group near-synonyms; a human audit of the categorisation is still worth one pass.

**Would I move it?** For a one-time pre-launch read: stay here. For a weekly or monthly cadence, or any n above ~50 where you need the exact counts to be auditable: move to a scripted setup. The deciding factor is frequency and auditability requirement, not whether the tool *can* run at scale.
