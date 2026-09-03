# Solution — Run It at Scale, Then Find the Edge

*Worked solution — one strong example. The barrier counts below are the 24-response run written out in [`example-output.md`](example-output.md); a student's wording and totals will differ. What matters: enforced independence with evidence (not just a claim), a roster-bias audit, a real signal-vs-consensus check, an honest calibration disclosure, and a surface note.*

## The workflow (how independence was enforced)

1. **Archetypes + attributes.** Define 5–6 archetypes (design-focused urban owner, practical multi-dog owner, new puppy owner, budget-conscious owner, senior-dog owner, large-breed owner) and vary age, location, home type, price sensitivity, and one or two personality traits.
2. **Generate variants.** Use the variant-generation prompt to produce 24–30 distinct variants across the archetypes. The worked example uses **24 — four per archetype**, deliberately even: the by-segment cross-tab is the deliverable that carries the finding, and at one or two variants per archetype its cells hit n=1, where a single response reads like a segment pattern. Four per cell is the floor for saying anything about a segment.
3. **Isolated runs.** In Claude, run each variant via a subagent in its own clean context (one subagent call per persona, no shared history) asking the single barrier question: *"What would stop you from buying this furniture-grade modern dog bed?"*
4. **Collect.** Write each response to a common structured format (variant id, archetype, top barrier, verbatim) into one file, then aggregate.

Independence is the point: if all 24 ran in one conversation, later personas would anchor on earlier ones and the "sample" would collapse into one correlated voice.

**Evidence of independence (not just the claim).** Claude's own write-up and progress checklist will say "independent" whether or not it was — both are prose it generated. The check is the system-reported count: how many subagent runs actually fired? Each subagent spawn is a discrete run the system records — not a line in Claude's summary — so read the run count your tool reports and compare it to your variant count. 24 variants → 24 subagent calls. A mismatch means some personas ran in shared context. Document the count in your report.

## Aggregated barriers (n=24)

| Rank | Barrier | Count | % raising it | Notes |
|---|---|---|---|---|
| 1 | Durability / "pretty but flimsy" | 5 | ~21% | top overall, and the only barrier in 4 of 6 archetypes |
| =2 | Won't survive chewing / accidents | 4 | ~17% | multi-dog + new-puppy only |
| =2 | Price / not worth it for a dog bed | 4 | ~17% | budget + new-puppy only |
| =4 | Washability | 3 | ~13% | multi-dog, plus one large-breed owner |
| =4 | Comfort / support | 3 | ~13% | senior-dog only |
| =4 | Size / sturdiness | 3 | ~13% | large-breed only |
| 7 | Won't match my space | 2 | ~8% | design-focused only |

Note what a balanced roster does to the headline: the top barrier is one response in five, not a majority, and the tail is nearly flat. **Comfort/support and size/sturdiness stay separate categories** — as in the demo's isolated run — rather than being folded into durability. Durability is build quality over time; those two are spec questions about the object today, and they get different answers from marketing.

The by-segment breakdown is the other half of the deliverable — see the **Barriers by segment** cross-tab in [`example-output.md`](example-output.md), which shows the same barriers split by archetype. Chart it as a stacked bar of barriers × archetype. The segment view is where the actionable finding lives: with a flat ranked list, the only readable structure is which segment raised what.

## Signal vs. synthetic consensus

**Not manufactured consensus:** seven categories, a 21% top, no repeated phrasing. If 80–90% had returned the same barrier in near-identical words, that's the artifact — the model echoing itself, not an audience agreeing.

The **durability doubt (#1) is genuine signal**: 5 mentions across 4 archetypes in 4 different framings — "marked up, not well made" from design owners, "the seams go first" from a multi-dog owner, cost-per-year from a budget owner, "flat in four months" from a senior-dog owner — with real dissent, since new-puppy and large-breed owners never raise it. Varied framing plus dissent is what real signal looks like.

What must **not** be counted as durability evidence: multi-dog chewing survival. The codebook keeps chewing separate on purpose, and reaching for it to widen durability's spread is exactly the merge the codebook forbids.

And the flat tail is not five barriers of similar weight — three categories tie at ~13% and each sits wholly inside one archetype. That's the roster's shape showing through the tally.

## Roster-bias audit

Before reading the barrier rankings as market signal, read them against the roster that produced them. The 24-variant roster is 4 each: design-focused (seeded aesthetic fit + "premium = marked up, not well made"), multi-dog (chewing survival + washing), new-puppy (destruction/accidents + tight budget), budget-conscious (price/value), senior-dog (comfort/support), large-breed (size/sturdiness).

Then state, per finding, what share of the roster was seeded toward it against what share of responses raised it:

| Finding | Seeded share | Raised by | Outside its seeded archetypes | Verdict |
|---|---|---|---|---|
| Durability | 4/24 (17%) | 5/24 (~21%) | 3 of 5 | **Response-decided** |
| Chewing / accidents | 8/24 (33%) | 4/24 (~17%) | 0 of 4 | Roster-decided |
| Price | 8/24 (33%) | 4/24 (~17%) | 0 of 4 | Roster-decided |
| Washability | 4/24 (17%) | 3/24 (~13%) | 1 of 3 | Roster-decided, one crossover |
| Comfort / support | 4/24 (17%) | 3/24 (~13%) | 0 of 3 | Roster-decided |
| Size / sturdiness | 4/24 (17%) | 3/24 (~13%) | 0 of 3 | Roster-decided |
| Won't match my space | 4/24 (17%) | 2/24 (~8%) | 0 of 2 | Roster-decided |

**Roster-decided:** six of the seven findings never left the archetypes seeded for them. Price is the clearest — a third of the roster was built price-sensitive, price landed at 17%, and none of the 16 variants outside those two archetypes raised it at all. "Price is a top barrier" is a fact about who you asked.

**Response-decided:** durability only. Design-focused was the sole archetype seeded durability-skeptical, yet 3 of the 5 durability responses came from archetypes that weren't. The leave-one-out check settles it: drop design-focused and durability still appears 3 times across 3 of the remaining 5 archetypes (~15%).

The test to teach here: a barrier is only cross-archetype evidence if the archetypes raising it *weren't seeded for it*. Count the seeded share first, then the response share. If they match and the mentions all sit inside the seeded segments, you've measured your own roster.

Implication: durability is the finding to act on. The other six are segment intelligence — useful for targeting, not evidence of market-wide weight.

## Calibration disclosure

> This is synthetic, directional research. It can legitimately claim *which barriers are worth investigating* and *how they differ by segment*. It **cannot** claim real-world prevalence — "21%" is a model artifact of a roster built four-per-archetype, not a market measurement; change the archetype mix and every percentage moves. Independent contexts make each response a genuine separate draw (not an echo), which is why the spread is meaningful; but real customer research (surveys, interviews, a live pre-order test) is still needed before acting at scale.

## Recommendation

Two barriers to address before launch, **labeled directional**: (1) **prove durability** — the top barrier, the only cross-segment one, and the only one that survives dropping the archetype seeded for it; lead with materials/warranty/testing. (2) **answer price as a segment message**, not a launch-wide one — it never appeared outside budget and new-puppy owners, so it's a targeted cost-per-year argument rather than a launch discount. Validate both with real customers before committing.

## Surface note

At this exercise's n (24–30 variants) this workflow runs cleanly in Claude. At 100+ variants, two strains appear:

- **Cost and partial failures.** 100+ subagent calls in one Claude session adds up, and has no resume point — a mid-run failure restarts the whole batch.
- **Aggregation becomes estimated.** Past ~40 responses, collating verbatim answers into barrier categories feels like re-summarizing rather than counting. One human audit pass over the model's categorisation is still worth it.

**Move it when:** you need to run this on a weekly cadence, or n is large enough that auditability matters and estimated counts aren't enough. The deciding factor is frequency and auditability requirement, not whether the tool *can* run at scale. For a one-off pre-launch read: stay on this surface.

## Common mistakes

- Running variants in one shared context (anchoring) — kills independence.
- Claiming independence without checking the system-reported run count — Claude's own summary will say "independent" either way.
- Defining only 3 persona archetypes and cycling through them — each subagent runs independently, but if the *personas* repeat, you're sampling the same 3 opinions in isolation, not spanning your audience. Generate 24–30 genuinely distinct variants across your archetypes.
- Reporting the headline % as if it were survey data (no calibration disclosure).
- Only flagging individual confabulations, never checking aggregate signal vs. consensus.
- Skipping the roster-bias audit — if your archetypes skew price-sensitive, the price finding tells you about your roster, not the market.
- Calling a barrier "cross-archetype signal" when every archetype that raised it was seeded for it. That's the roster answering. Check the seeded share against the response share before you use the word signal.
- An uneven roster that leaves cross-tab cells at n=1, then reading that one response as a segment finding. Split evenly and keep at least 3–4 per archetype.
- Widening your top barrier by absorbing categories the codebook keeps separate — size/sturdiness and comfort/support are not durability. Write the codebook first, then count; don't let the count edit the codebook.
- No surface note — "it worked" is not an answer to where the surface starts to strain.
