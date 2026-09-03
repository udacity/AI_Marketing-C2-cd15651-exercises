# Sample Output — Recommendation Memo

*Actual Claude output — the framework applied to the three provided profiles + the DIY baseline, then a memo. One run; a different well-argued call is acceptable.*

## Scored comparison (1–5)

| Dimension | Penmark | CopyFlow | BrandForge | DIY baseline |
|---|---|---|---|---|
| Capability fit **(heavy)** | 5 | 2 | 4 | 4 |
| Brand-voice control / brand-safety **(heavy)** | 4 | 2 | 5 | 3 |
| Fit with your stack | 2 | 5 | 5 | 2 |
| Cost vs. value | 2 | 5 | 3 | 5 |
| Data & privacy **(heavy)** | 5 | 4 | 2 | 3 |
| Learning curve / adoption | 3 | 5 | 3 | 5 |
| **Total** | 21 | **23** | 22 | 22 |
| **Heavy three only** | **14** | 8 | 11 | 10 |

*Weighted heaviest: capability fit, brand-voice/brand-safety (it's a copywriting tool — on-brand output **is** the job), and data & privacy (a train-on-inputs clause is a real risk for brand copy). **CopyFlow tops the raw total and comes last on the heavy three** — its 23 is built from stack fit, price, and ease, none of which is the job. That gap between the two rows is the whole point of weighting.*

## Findings

- **Penmark** — best output and the tightest voice control in the field, but no prohibited-claims list and no compliance review: it will write an unsupported claim beautifully. Copy-paste-only and premium-priced; the quality edge over a well-briefed general model is thin on everyday copy.
- **CopyFlow** — cheap and well-integrated, but generic output needs heavy editing and tone drifts across a long batch. Its banned-words filter is the only dedicated safety feature here, and it catches wording, not claims. Highest raw total, last on the heavy three.
- **BrandForge** — strongest on brand-voice/safety: custom voice profiles plus the only compliance-approval workflow with an audit trail. But the standard tier may train on your inputs, and the no-training tier costs *more than Penmark*. Privacy drags it down.
- **DIY baseline** — tested across two models with a goal-rich brief: on-brand and close to BrandForge on everyday copy, at ~no marginal cost. No guardrails and no audit trail — brand-safety is whatever the brief enforces plus a human read. **Checked our existing terms** as the profile asks: our current plan is a business tier that does not train on inputs, which is what makes that 3 a known quantity rather than an unknown. Loses on integration.

## Baseline test — the evidence behind that 4

**The test piece:** a Flowline upgrade email — the most ordinary thing in our copy queue, which is the point. Same brief, run through two general models we already pay for.

**The brief** — goal-rich, not a prompt:

> - **Audience:** free-tier users 30+ days in, two or more active projects, sync never used — they've hit the free tier's edges without upgrading.
> - **Goal:** one click through to the Premium comparison page. Not a trial signup, not a reply.
> - **Context:** Premium adds cross-device sync, unlimited projects, workflow shortcuts. They already know what the app does.
> - **Voice:** plain, second-person, calm — a colleague pointing something out, not a pitch. Short sentences, contractions fine.
> - **Avoid:** "unlock," "supercharge," "next level"; exclamation marks; emoji; fake urgency; discounts; re-explaining the product.
> - **Format:** subject under 45 characters, body under 60 words, one bracketed CTA.

**Model 1 — on brand, shippable as-is:**

> **Subject:** Your projects, on your phone too
> Hi [First name] — you've got three projects running in Flowline, all of them on this laptop. Premium syncs them to your phone, so the list you left at your desk is the same list on the train. **[See what's in Premium →]**

**Model 2 — competent, but it drifts:**

> **Subject:** Ready to take Flowline further?
> Hi [First name], you're clearly getting a lot out of Flowline — three active projects and counting. Premium unlocks cross-device sync, unlimited projects, and workflow shortcuts that make your day noticeably faster. Upgrade today and take your productivity to the next level. **[Upgrade now]**

*Same brief, same constraints — Model 2 broke three of them: "unlocks" and "next level" straight off the avoid list, the feature dump the brief said to skip, and a CTA pointed at checkout instead of the comparison page. One steering line fixed it, and only for that session.*

**What the test showed:** with the brief in front of it, a general model writes copy we would ship without editing — that is the 4, and it's what puts the baseline next to BrandForge on everyday pieces. **What it didn't show:** any ability to hold the voice *without* the brief. Both runs stayed on tone because the constraints were re-pasted into the session; nothing in either model remembers them tomorrow, and one email says nothing about drift across a twenty-email batch. That gap — not output quality — is what a saved voice profile buys, and it's why brand-voice control scores 3 while capability scores 4.

## Decision size — a two-way door

Every option is a monthly subscription and the copy lands in files we own: nothing to migrate, nothing built around the tool, cancel any month. Switching cost is low and nothing is locked in, so this is a **two-way door** and doesn't warrant exhaustive diligence — which is what lets the call be "adopt now, revisit in a quarter." On durability, **Penmark** is the only real risk (small, young startup, limited track record); **CopyFlow** and **BrandForge** are established and stable. That risk stays minor *because* the door swings both ways — it would be decisive if this were a deep integration or a multi-year commitment.

## Recommendation

> **Adopt the DIY baseline now — buy nothing new.** A goal-rich brief plus the general model we already pay for covers our copywriting need at no added cost and no new data risk (checked: our current business tier does not train on inputs). None of the three specialized tools beats that baseline by enough to justify its price and risk: Penmark's edge is too narrow, CopyFlow solves a problem we don't have, and BrandForge's privacy terms flip its price above Penmark. **Tradeoffs accepted:** no native integration (manual copy-paste) at current volume, and no brand-safety guardrails or audit trail — our brand rules are enforced by the brief and a human read, not by the tool. **Revisit next quarter** — with a BrandForge *no-training-tier* pilot if copy volume outgrows copy-paste, or sooner if we start making claims that need an approval trail.
