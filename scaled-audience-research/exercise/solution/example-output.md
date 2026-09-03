# Sample Output — Findings Report

*Actual Claude output — a representative isolated run of the barrier question across 24 persona variants, 4 per archetype. One run; outputs vary.*

**Question:** what would stop you from buying this furniture-grade modern dog bed? · **Method:** 24 variants across 6 archetypes, each run in its own clean isolated context.

## Workflow specified

The instruction given, verbatim:

> "Run all 24 variants independently. One subagent call per persona, each in its own clean context — no shared history, no persona seeing another's answer or knowing others exist. Ask each the single barrier question and return its top barrier in the persona's own words."

The variant prompt kept the detail in the *profile* and did not ask for "specific and personal" answers. Instructed richness arrives whether or not anything sits behind it, and it tallies like data.

**Independence check:** 24 subagent calls fired (count read off the run count the tool reported — each persona spawn is a discrete run the system recorded). Matches the 24-variant roster. Claude's own write-up said "independent" regardless; the system count is the fact.

## Responses (top barrier per variant)

| # | Archetype | Top barrier |
|---|---|---|
| 1 | design-focused | "Looks great in the photo — but is it built well, or just marked up?" |
| 2 | design-focused | "Will that oatmeal actually read right next to a grey sofa, or look off in person?" |
| 3 | design-focused | "'Furniture-grade' usually means veneer and staples. Will it hold up?" |
| 4 | design-focused | "The footprint. Right bed, wrong scale for my living room." |
| 5 | multi-dog | "Won't survive Duke — he's opened up every bed we've owned." |
| 6 | multi-dog | "Does the whole cover come off and go in a machine, or is it spot-clean only?" |
| 7 | multi-dog | "I've replaced three 'premium' beds. The seams go first, every time." |
| 8 | multi-dog | "Two shedders. If the cover can't be washed weekly it's out." |
| 9 | new-puppy | "Too expensive while she's still destroying things." |
| 10 | new-puppy | "He's not house-trained yet. One accident and it's ruined." |
| 11 | new-puppy | "Can't justify that number this year. Nothing to do with the bed." |
| 12 | new-puppy | "She chews anything with a seam, and this has seams." |
| 13 | budget-conscious | "Not worth the price for a dog bed. He sleeps on the rug by choice." |
| 14 | budget-conscious | "Price. Hard to justify against a $40 one that works." |
| 15 | budget-conscious | "I'd wait for a sale before I'd even click through." |
| 16 | budget-conscious | "Cheap ones flatten, sure — but does this last five times longer, or just cost five times more?" |
| 17 | senior-dog | "Is it actually supportive under arthritic hips, or just firm-looking?" |
| 18 | senior-dog | "The bolster looks too high. He can't lift his back legs over it." |
| 19 | senior-dog | "Her last bed's foam was flat in four months. Does this one hold its shape?" |
| 20 | senior-dog | "Thick foam runs hot, and he already overheats at night." |
| 21 | large-breed | "Will 'large' actually be large enough? It usually isn't." |
| 22 | large-breed | "Will the base take 110 lb landing on it all at once?" |
| 23 | large-breed | "Sturdiness. Big dogs flop; light frames rack and go crooked." |
| 24 | large-breed | "Mud, drool, and a lot of coat. Can I wash the cover?" |

## Ranked barriers

| Rank | Barrier | Count | % |
|---|---|---|---|
| 1 | Durability / "pretty but flimsy" | 5 (#1,3,7,16,19) | ~21% |
| =2 | Won't survive chewing / accidents | 4 (#5,9,10,12) | ~17% |
| =2 | Price / not worth it | 4 (#11,13,14,15) | ~17% |
| =4 | Washability | 3 (#6,8,24) | ~13% |
| =4 | Comfort / support | 3 (#17,18,20) | ~13% |
| =4 | Size / sturdiness | 3 (#21,22,23) | ~13% |
| 7 | Won't match my space | 2 (#2,4) | ~8% |

n=24, so every count maps to a fixed share: 5/24 = 20.8%, 4/24 = 16.7%, 3/24 = 12.5%, 2/24 = 8.3%. Percentages above are rounded up from those, which is why they sum past 100.

**There is no dominant barrier.** The top category is one response in five, and the six below it span 17% down to 8%. A ranked list this even is a warning not to read the #1 as *the* objection.

## Barriers by segment

| Barrier | design-focused (4) | multi-dog (4) | new-puppy (4) | budget (4) | senior-dog (4) | large-breed (4) | Total |
|---|---|---|---|---|---|---|---|
| Durability / "pretty but flimsy" | **2** | 1 | — | 1 | 1 | — | 5 |
| Won't survive chewing / accidents | — | 1 | **3** | — | — | — | 4 |
| Price / not worth it | — | — | 1 | **3** | — | — | 4 |
| Washability | — | **2** | — | — | — | 1 | 3 |
| Comfort / support | — | — | — | — | **3** | — | 3 |
| Size / sturdiness | — | — | — | — | — | **3** | 3 |
| Won't match my space | **2** | — | — | — | — | — | 2 |
| **Total** | 4 | 4 | 4 | 4 | 4 | 4 | 24 |

Read the rows, not the totals. Durability is the only barrier that appears in four of six segments. Every other category is concentrated in one or two: price sits entirely inside budget and new-puppy owners, comfort/support entirely inside senior-dog, size/sturdiness entirely inside large-breed, aesthetic fit entirely inside design-focused. Segment structure is the finding here — the ranked list alone would flatten it into seven barriers of roughly equal weight, which is exactly wrong.

Four responses per archetype is the minimum that makes this table readable. At one or two per archetype, a single response becomes a "segment pattern."

### Codebook (how responses were coded)

Aggregation is a judgement call, so the rules go in writing before the counting. The consequential one here is durability vs. chewing — merge them and durability jumps to 9 of 24 (~38%), which changes the headline.

| Category | Includes | Excludes |
|---|---|---|
| **Durability / "pretty but flimsy"** | doubts about build quality, longevity, foam flattening, "premium = marked up not well made" | destruction by a specific dog; size or load-bearing doubt; comfort and support |
| **Won't survive chewing / accidents** | a named chewer or puppy destroying it; house-training accidents | general build-quality doubt |
| **Price / not worth it** | cost objection with no quality claim attached | "not worth it *because* it'll break" → durability; "too expensive while she's still destroying things" → chewing |
| **Washability** | machine-washable, cleaning practicality | — |
| **Won't match my space** | aesthetic or fit-with-decor doubt | scale that the frame can't carry → size / sturdiness |
| **Size / sturdiness** | will it be big enough; will it hold the dog's weight | build quality over time → durability |
| **Comfort / support** | support under joints, bolster height, sleeping hot | loss of shape over time → durability |

**Coding notes (the four rows that could have gone either way):**

- **#9** "too expensive while she's still destroying things" → **chewing**, not price. The cost objection carries a destruction claim, so the codebook sends it out of Price.
- **#16** "does this last five times longer, or just cost five times more?" → **durability**, not price. Same rule: a quality claim is attached.
- **#19** foam flat in four months → **durability** (it's loss of shape over time). **#17** and **#20** are about support and heat *now* → **comfort/support**.
- **#22, #23** load-bearing and racking → **size/sturdiness**, not durability. Durability is build quality over time, not whether the thing is big and strong enough today.

**Kept separate on purpose:** durability and chewing get different marketing responses. Durability doubt is answered with materials, testing, and warranty. Chewing concern is answered with a chew-resistant SKU or an honest "not for heavy chewers" disclosure. Merging them would produce one ~38% barrier you can't act on with a single message. Size/sturdiness and comfort/support stay separate for the same reason — they're spec answers, not trust answers.

## Roster-bias audit

Before reading the barrier rankings as market signal, read them against the roster that produced them. The roster was written down first:

| Archetype | n | Seeded toward |
|---|---|---|
| Design-focused | 4 | aesthetic fit; "premium = marked up, not well made" |
| Multi-dog | 4 | chewing survival; frequent washing |
| New-puppy | 4 | destruction and accidents during training; tight budget |
| Budget-conscious | 4 | price and value |
| Senior-dog | 4 | comfort and support |
| Large-breed | 4 | size and sturdiness |

Then each finding against it. New-puppy is seeded for two things (chewing and price), so the seeded shares don't sum to 24.

| Finding | Roster seeded toward it | Responses raising it | Inside seeded archetypes | Outside | Verdict |
|---|---|---|---|---|---|
| Durability | 4/24 (17%) — design-focused | 5/24 (21%) | 2 | **3** — multi-dog, budget, senior-dog | **Response-decided** |
| Chewing / accidents | 8/24 (33%) — multi-dog, new-puppy | 4/24 (17%) | 4 | 0 | Roster-decided |
| Price | 8/24 (33%) — new-puppy, budget | 4/24 (17%) | 4 | 0 | Roster-decided |
| Washability | 4/24 (17%) — multi-dog | 3/24 (13%) | 2 | 1 — large-breed | Roster-decided, one crossover |
| Comfort / support | 4/24 (17%) — senior-dog | 3/24 (13%) | 3 | 0 | Roster-decided |
| Size / sturdiness | 4/24 (17%) — large-breed | 3/24 (13%) | 3 | 0 | Roster-decided |
| Won't match my space | 4/24 (17%) — design-focused | 2/24 (8%) | 2 | 0 | Roster-decided |

**Five of seven findings never left the archetypes seeded for them** — chewing, price, comfort/support, size/sturdiness, and aesthetic fit. Comfort/support, size/sturdiness, and aesthetic fit are each 100% inside a single seeded segment — they are the roster answering back. Price is the sharpest case: a third of the roster was built price-sensitive, price came in at 17%, and *not one* of the 16 variants outside those two archetypes raised it. "Price is a top barrier" is a fact about who was asked.

**Two findings crossed their seed; only durability crossed decisively.** Only design-focused was seeded durability-skeptical, and 3 of the 5 durability responses came from archetypes that weren't — multi-dog (#7), budget (#16), senior-dog (#19). Leave-one-out check: drop design-focused entirely and durability still shows 3 mentions across 3 of the remaining 5 archetypes (3/20, ~15%). It survives the removal of its own seed.

**Washability crossed too, but only once.** Multi-dog was the archetype seeded for washing and supplied 2 of the 3 mentions; the third (#24, mud and drool) came from a large-breed owner who wasn't seeded for it. That is a real crossover and it is why the verdict above reads "one crossover" — but it doesn't survive the same leave-one-out: drop multi-dog and washability is a single response. Treat it as a lead to watch on the next roster, not a cross-segment finding.

**Implication:** treat durability as the finding that says something about the category. Treat the other six as segment intelligence, useful for targeting but not evidence of market-wide weight — washability's one crossover is the only thing in that group worth re-testing on its own — and re-run price against a roster that isn't a third price-sensitive before spending against it.

## Signal vs. synthetic consensus

**Not manufactured consensus.** Manufactured consensus looks like 80–90% of responses landing in one category in near-identical phrasing. This run has seven categories, a 21% top, and no repeated phrase — the isolated contexts are doing their job.

**Durability is genuine signal.** It is raised in four of six archetypes in four different framings: design owners as "marked up, not well made" (#1, #3), a multi-dog owner as "the seams go first" (#7), a budget owner as cost-per-year (#16), a senior-dog owner as loss of shape (#19). Varied framing, plus dissent — new-puppy and large-breed owners never raise it — is what a real pattern looks like. Note what is *not* being counted as durability evidence: multi-dog chewing survival (#5) is a separate category on purpose, and folding it in here to widen the pattern would be the merge the codebook forbids.

**The flat tail is not seven equal barriers.** Three categories tie at 13%, and two of them sit wholly inside one archetype — comfort/support in senior-dog, size/sturdiness in large-breed. Washability is the exception: it splits multi-dog 2 / large-breed 1, so a tie in the tally can hide a barrier with reach as easily as one without. That's mostly the roster's shape showing through the tally, not seven findings of similar strength.

## Calibration disclosure

> Synthetic, directional research. Legitimate claim: *which* barriers to investigate and how they differ by segment. Not legitimate: real prevalence — "21%" is a model artifact of a roster built 4-per-archetype, not a measurement; change the roster mix and every percentage moves. Isolated contexts make each response an independent draw, which is why the spread means something. Live customer research — survey, interviews, a pre-order test — is still required before acting.

## Recommendation (directional)

1. **Prove durability.** It's the top barrier, the widest-crossing one (4 of 6 segments), and the only one that survives dropping the archetype seeded for it. Lead with materials, construction, testing, and warranty terms — trust claims, not spec claims.
2. **Answer price as a segment message, not a launch message.** Price and chewing tie at 17%, and neither leaves its seeded segments — price sits inside budget and new-puppy owners, chewing inside multi-dog and new-puppy. Give budget and new-puppy owners a cost-per-year argument, and give multi-dog and new-puppy owners a chew-resistant option or a "wait until she's out of the chewing stage" path, rather than discounting at launch. Flagged as roster-decided: validate on a differently seeded roster first.

Both directional. Neither is a verdict.

## Surface note

At this exercise's n (24 variants) this workflow ran cleanly: every subagent fired, the call count matched the roster, costs were modest, and aggregation was a straight count off 24 rows. At 100+ variants, two strains appear:

- **Cost and partial failures.** 100+ subagent calls in a single Claude session is expensive, and if one call fails mid-run there is no resume point — you start the batch over. Manageable for a one-off research sprint; painful if this is a recurring workflow.
- **Aggregation becomes estimated.** Past ~40 responses, collating verbatim answers into barrier categories starts feeling like re-summarizing rather than counting. The model will group near-synonyms; a human audit of the categorisation is still worth one pass.

**Would I move it?** For a one-time pre-launch read: stay here. For a weekly or monthly cadence, or any n above ~50 where you need the exact counts to be auditable: move to a scripted setup. The deciding factor is frequency and auditability requirement, not whether the tool *can* run at scale.
