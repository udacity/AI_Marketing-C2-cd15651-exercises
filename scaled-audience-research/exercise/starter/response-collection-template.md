# Response Collection Template

*Provided template. Every isolated run returns one response; this is where they land. Set the file up **before** you start running, not after — retro-fitting a format across two dozen scattered answers is how variants go missing and how the run count stops matching the row count.*

---

## The file

One row per variant. Nothing else in the file.

```
variant_id | archetype | top_barrier | verbatim
```

| Column | What goes in it |
|---|---|
| `variant_id` | The number from your variant set — `1`, `2`, `3`… Keep them in order, and keep the gaps if a run fails. A missing id is evidence; a silently renumbered file is not. |
| `archetype` | Which archetype this variant belongs to. Use the exact same label every time — `new-puppy`, not `new puppy` on one row and `puppy owner` on the next. Your cross-tab is only as good as this column. |
| `top_barrier` | Your **coded** category, from your codebook. Not the persona's words — the bucket you put them in. |
| `verbatim` | The persona's actual words, quoted. One sentence is enough. |

Both of the last two columns matter, and for different reasons. `top_barrier` is what you count. `verbatim` is what lets you check the count — and what lets a reader disagree with your coding, which they can't do if you only kept the bucket.

---

## Worked row

```
7 | multi-dog | Durability | "I've replaced three 'premium' beds. The seams go first, every time."
```

Coded as Durability, not as *Won't survive chewing* — no specific dog is named, the doubt is about how the thing is built. That distinction is a judgement call, which is exactly why the verbatim stays in the file and why you write the codebook down first.

---

## Two checks before you aggregate

**Row count = run count.** The number of rows here must equal the number of runs your tool reports. If you ran 24 variants and have 23 rows, one failed silently — find it before you start counting, because a missing row is a missing response, not a rounding error.

**Every archetype label appears the same number of times** (or you can say why it doesn't). Uneven cells aren't fatal, but you have to *know* they're uneven — a segment claim built on one response reads exactly like a segment claim built on four.

---

**Why a fixed format at all:** you are going to cross-tabulate barrier against archetype. That table is the deliverable that carries the finding, and it is only possible if every response was written down the same way. Decide the format once, at the start, and the aggregation is arithmetic. Decide it at the end and it is archaeology.
