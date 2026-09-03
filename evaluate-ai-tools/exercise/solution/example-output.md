# Sample Output — Recommendation Memo

*Actual Claude output — the framework applied to the three provided profiles + the DIY baseline, then a memo. One run; a different well-argued call is acceptable.*

## Scored comparison (1–5)

| Dimension | Penmark | CopyFlow | BrandForge | DIY baseline |
|---|---|---|---|---|
| Capability fit **(heavy)** | 5 | 2 | 4 | 4 |
| Brand-voice control / brand-safety **(heavy)** | 4 | 2 | 5 | 3 |
| Fit with stack | 2 | 5 | 5 | 2 |
| Cost vs. value | 2 | 5 | 3 | 5 |
| Data & privacy **(heavy)** | 5 | 4 | 2 | 3 |
| Learning curve | 3 | 5 | 3 | 5 |
| **Total** | 21 | **23** | 22 | 22 |
| **Heavy three only** | **14** | 8 | 11 | 10 |

*Weighted heaviest: capability fit, brand-voice/brand-safety (it's a copywriting tool — on-brand output **is** the job), and data & privacy (a train-on-inputs clause is a real risk for brand copy). **CopyFlow tops the raw total and comes last on the heavy three** — its 23 is built from stack fit, price, and ease, none of which is the job. That gap between the two rows is the whole point of weighting.*

## Findings

- **Penmark** — best output and the tightest voice control in the field, but no prohibited-claims list and no compliance review: it will write an unsupported claim beautifully. Copy-paste-only and premium-priced; the quality edge over a well-briefed general model is thin on everyday copy.
- **CopyFlow** — cheap and well-integrated, but generic output needs heavy editing and tone drifts across a long batch. Its banned-words filter is the only dedicated safety feature here, and it catches wording, not claims. Highest raw total, last on the heavy three.
- **BrandForge** — strongest on brand-voice/safety: custom voice profiles plus the only compliance-approval workflow with an audit trail. But the standard tier may train on your inputs, and the no-training tier costs *more than Penmark*. Privacy drags it down.
- **DIY baseline** — tested across two models with a goal-rich brief: on-brand and close to BrandForge on everyday copy, at ~no marginal cost. No guardrails and no audit trail — brand-safety is whatever the brief enforces plus a human read. **Checked our existing terms** as the profile asks: our current plan is a business tier that does not train on inputs, which is what makes that 3 a known quantity rather than an unknown. Loses on integration.

## Recommendation

> **Adopt the DIY baseline now — buy nothing new.** A goal-rich brief plus the general model we already pay for covers our copywriting need at no added cost and no new data risk (checked: our current business tier does not train on inputs). None of the three specialized tools beats that baseline by enough to justify its price and risk: Penmark's edge is too narrow, CopyFlow solves a problem we don't have, and BrandForge's privacy terms flip its price above Penmark. **Tradeoffs accepted:** no native integration (manual copy-paste) at current volume, and no brand-safety guardrails or audit trail — our brand rules are enforced by the brief and a human read, not by the tool. **Revisit** with a BrandForge *no-training-tier* pilot if copy volume outgrows copy-paste, or sooner if we start making claims that need an approval trail.
