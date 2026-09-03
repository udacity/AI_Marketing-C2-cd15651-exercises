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

**What the cost row assumes.** Priced for the three seats we actually have: CopyFlow $54/mo, BrandForge $199/mo flat, Penmark $360/mo, BrandForge's no-training tier $447/mo. Penmark and the no-training tier are per-seat, so they scale with headcount; BrandForge's standard plan doesn't move until seat eleven. A larger team would flatter the flat rate and punish the per-seat ones — state the size you're pricing for, because the ranking moves with it.

## Findings

- **Penmark** — best output and the tightest voice control in the field, but no prohibited-claims list and no compliance review: it will write an unsupported claim beautifully. Copy-paste-only and premium-priced; the quality edge over a well-briefed general model is thin on everyday copy.
- **CopyFlow** — cheap and well-integrated, but generic output needs heavy editing and tone drifts across a long batch. Its banned-words filter is the only dedicated safety feature here, and it catches wording, not claims. Highest raw total, last on the heavy three.
- **BrandForge** — strongest on brand-voice/safety: custom voice profiles plus the only compliance-approval workflow with an audit trail. But the standard tier may train on your inputs, and the no-training tier costs *more than Penmark*. Privacy drags it down.
- **DIY baseline** — tested across two models with a goal-rich brief: on-brand and close to BrandForge on everyday copy, at ~no marginal cost. No guardrails and no audit trail — brand-safety is whatever the brief enforces plus a human read. **Checked our existing terms** as the profile asks: our current plan is a business tier that does not train on inputs, which is what makes that 3 a known quantity rather than an unknown. Loses on integration.

## Baseline test — the evidence behind that 4

**The test piece:** the Cobbleway Overtrousers cross-sell email from the brief — the most ordinary thing in our copy queue, which is the point. Same brief, run through two general models we already pay for.

**The brief** — goal-rich, not a prompt, written up from the brand asset:

> - **Audience:** bought the Commuter Shell 8–14 months ago, nothing since. They ride or walk to work most days and already like the shell.
> - **Goal:** one click through to the Overtrousers page. Not a reply, not a browse.
> - **Context:** the wet season is starting. The Overtrousers pull on over work trousers without taking your shoes off, pack into a jersey pocket, and cost less than the shell.
> - **Voice:** plain, dry, second person, specific about the material and the fit. Weather is a fact you dress for, not an enemy. Honest about limits — waterproof, not warm.
> - **Avoid:** "conquer," "brave the elements," "unstoppable," "gear up," "adventure," "performance"; exclamation marks; emoji; weather-fear; discounts; re-explaining what rain is.
> - **Format:** subject under 45 characters, body under 70 words, one bracketed CTA.

**Model 1 — on brand, shippable as-is:**

> **Subject:** The trousers that go over trousers
> You've had the Commuter Shell through a winter. The Overtrousers are the other half: they pull on over your work trousers without taking your shoes off, and pack down into a jersey pocket. Waterproof, not warm — you'll still want a layer under them in February. **[See the Overtrousers →]**

**Model 2 — competent, but it drifts:**

> **Subject:** Ready to conquer the wet season?
> Hi [First name] — rain doesn't have to ruin your ride! Our Overtrousers deliver waterproof performance with a breathable membrane, fully taped seams and reflective trim, so you can brave the elements in total confidence. Gear up now and make this your driest winter yet. **[Shop all outerwear]**

*Same brief, same constraints — Model 2 broke four of them: "conquer," "performance," "brave the elements" and "gear up" straight off the avoid list, an exclamation mark, the weather-fear opener the voice rules out, and a CTA pointed at the whole outerwear category instead of the Overtrousers page. It also dumped features the brief didn't ask for and skipped the limits line that makes the brand sound like itself. One steering line fixed it, and only for that session.*

**What the test showed:** with the brief in front of it, a general model writes copy we would ship without editing — that is the 4, and it's what puts the baseline next to BrandForge on everyday pieces. **What it didn't show:** any ability to hold the voice *without* the brief. Both runs stayed on tone because the constraints were re-pasted into the session; nothing in either model remembers them tomorrow, and one email says nothing about drift across a twenty-email batch. That gap — not output quality — is what a saved voice profile buys, and it's why brand-voice control scores 3 while capability scores 4.

## Decision size — a two-way door

Every option is a monthly subscription and the copy lands in files we own: nothing to migrate, nothing built around the tool, cancel any month. Switching cost is low and nothing is locked in, so this is a **two-way door** and doesn't warrant exhaustive diligence — which is what lets the call be "adopt now, revisit in a quarter." On durability, **Penmark** is the only real risk (small, young startup, limited track record); **CopyFlow** and **BrandForge** are established and stable. That risk stays minor *because* the door swings both ways — it would be decisive if this were a deep integration or a multi-year commitment.

## Recommendation

> **Adopt the DIY baseline now — buy nothing new.** A goal-rich brief plus the general model we already pay for covers our copywriting need at no added cost and no new data risk (checked: our current business tier does not train on inputs). None of the three specialized tools beats that baseline by enough to justify its price and risk: Penmark's edge is too narrow, CopyFlow solves a problem we don't have, and BrandForge's privacy terms flip its price above Penmark. **Tradeoffs accepted:** no native integration (manual copy-paste) at current volume, and no brand-safety guardrails or audit trail — our brand rules are enforced by the brief and a human read, not by the tool. **Revisit next quarter** — with a BrandForge *no-training-tier* pilot if copy volume outgrows copy-paste, or sooner if we start making claims that need an approval trail.
