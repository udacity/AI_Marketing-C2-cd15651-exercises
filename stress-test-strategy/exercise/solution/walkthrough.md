# Solution — Stress-Test a Strategy, Surface the Assumptions

*Worked solution — one strong example. What matters: a real adversarial-reviewer prompt, ranked assumptions, one critique honestly discounted, a cheap test for the top risk, and a tight revised position.*

**Strategy under test:** move cross-device sync (currently free, used daily by most active free users) behind the Premium paywall.

## 1. Naive evaluation (saved for contrast)

Asked "is this a good idea?", Claude broadly agrees: sync is sticky, competitors charge for it, high-intent users will convert. Agreeable and low-value — it never names what has to be *true* for the play to work.

## 2. Adversarial-reviewer prompt (used)

> "Act as a skeptical growth lead. Your job is to find the 3–5 assumptions this strategy quietly depends on and would fail on, and to name the strongest case against it. Be specific about second-order effects."

## 3. The assumptions, ranked by damage if wrong

1. **Users convert rather than resent.** The whole play rests here, and nothing tests it.
2. **The free tier stays attractive enough** to keep feeding future conversion.
3. **Sync isn't easily replaced.** If it is, they bridge devices another way or leave.
4. **The support and goodwill cost is tolerable** at rollout.

Rank them by damage, not likelihood — the ordering is what decides which one earns a test. Note this is **not** the order the reviewer listed them in: it put replaceability second, because that is the obvious rebuttal to the play's own logic. But being wrong about replaceability is a *bounded* miss — you lose some of this cohort, and the same pilot that answers "convert vs. resent" would surface it. Being wrong about the free tier damages every future cohort's conversion pipeline, compounds quietly, and is the slowest of the four to detect and the hardest to walk back. On damage, it outranks replaceability. Promoting it is the judgment call; the reviewer's order was a listing order, not a ranking.

## 4. One critique I'd discount

Critique 4 — *"expect complaints, reviews, and churn spikes at rollout."* The spike is real but **transient**, and it is the cost of any pricing change; the critique treats launch-week noise as a standing brand cost. Discount the framing, keep the operational point: staff support for launch week and grandfather existing users. The reviewer's job is to stress the thinking, not to be right about everything.

## 5. Cheap test for the top risk

Before a full rollout, gate sync behind Premium for a **small random slice of existing free users** — the group who would otherwise be grandfathered, and the only group whose sync actually disappears — and watch 30–60 day conversion *and* churn/complaint rates against a control. Cheap, reversible, and it answers "convert vs. resent" before we bet the free tier on it. *(Illustrative test design — swap for your own.)*

## 6. Revised position (one tight statement)

> **Recommendation:** don't roll this out broadly yet — pilot it on a small slice of existing free users first, carved out of the grandfathering, since they are the only group whose sync actually disappears. **Deciding reason:** the whole play rests on "users convert, not churn," and that's exactly the untested assumption. **What would change my call:** if the pilot shows conversion lift without a churn/complaint spike, expand it.

## Common mistakes

- Treating the adversarial output as the answer instead of ranking and judging it.
- Skipping the "discount one critique" step — the AI's pushback isn't automatically right.
- A "cheap test" that isn't cheap ("launch it and monitor").
