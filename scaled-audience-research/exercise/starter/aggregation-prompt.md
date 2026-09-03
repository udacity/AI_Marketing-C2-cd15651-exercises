# Scaled Research — Aggregation Prompt

*Provided template. Once every variant has run and your collection file is complete, paste it into Claude with this prompt to produce the ranked barriers, the by-segment cross-tab, and the checks that have to travel with them.*

---

```
I ran scaled synthetic audience research. Each persona variant answered one
barrier question in its own isolated context. My collected responses are pasted
below, one row per variant: variant_id | archetype | top_barrier | verbatim.

Before aggregating, state these back to me so I can check them:
- The number of rows you can see.
- The number of distinct archetypes, and how many variants fall in each.

Then:

1. Rank the barriers. For each: the count, the percentage of total responses, and
   the variant_ids behind it. Show the denominator you used.

2. Build a cross-tab of barrier (rows) by archetype (columns), with both margins
   totalled. This is the deliverable — the ranked list on its own flattens the
   finding.

3. For each barrier, say whether it appears across multiple archetypes or sits
   inside one or two. Name any barrier that is concentrated in a single archetype.

4. Flag anything the counts cannot support:
   - Any cell resting on one or two responses.
   - Any barrier whose percentage is an artifact of how many variants I ran
     (e.g. exact fractions of the sample size).
   - Any two barrier categories close enough that recoding one would change the
     ranking.

5. Signal vs. synthetic consensus. Quote the verbatims for the top barrier and
   judge: is this genuine variation — different archetypes, different wording,
   dissent present — or the same sentence returned repeatedly? Say which, and
   show the evidence you used.

Produce the output in this format:

RANKED BARRIERS (n = [total])
[rank] | [barrier] | [count] | [%] | [variant_ids]
...

BARRIERS BY SEGMENT
[the cross-tab, both margins totalled]

WHAT THE SEGMENTS SHOW
- [barrier]: [across N of M archetypes / concentrated in X]
...

WHAT THE COUNTS WON'T SUPPORT
- [thin cells, fraction artifacts, coding-sensitive margins]

SIGNAL VS. CONSENSUS
Verdict: [genuine variation / manufactured consensus / mixed]
Evidence: [what in the responses decided it]

RESPONSES:
[Claude reads the collected rows you paste below.]
```

---

**What to do with the output.** Two things it cannot do for you, and both are graded:

**The roster-bias audit is yours.** Claude can tell you price came up in 4 of 24 responses. It cannot tell you whether that is because the market cares about price or because you seeded four price-sensitive archetypes. Read every finding against the archetype mix you wrote down *before* you ran, and split them: which findings did your roster decide, and which did the responses decide? A finding that simply mirrors your seed proportions is the roster talking.

**Check the arithmetic, don't accept it.** The counts should reconcile against your row count, and both cross-tab margins should sum to the same total. This is the one place in the exercise where the model is doing something you can verify exactly — so verify it.

**And watch the percentage.** At two dozen responses every share is a coarse fraction; a single recoded answer moves it by four points. That number will still *look* like survey data when it reaches a slide, which is the precise reason the calibration disclosure has to travel with it.
