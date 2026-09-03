# Solution — Compare the Field, Write the Memo

*Worked solution — one strong example. Scores are judgment calls from the provided profiles; a defensible submission may weight differently and reach a different call, as long as the reasoning holds. Scale: 1 (poor) – 5 (excellent).*

## Scored comparison (four-way)

| Dimension (weight) | Penmark (A) | CopyFlow (B) | BrandForge (C) | DIY baseline |
|---|---|---|---|---|
| Capability fit **(heavy)** | 5 | 2 | 4 | 4* |
| Brand-voice control / brand-safety **(heavy)** | 4 | 2 | 5 | 3* |
| Fit with stack | 2 | 5 | 5 | 2 |
| Cost vs. value | 2 | 5 | 3 | 5 |
| Data & privacy **(heavy)** | 5 | 4 | 2 | 3* |
| Learning curve / adoption | 3 | 5 | 3 | 5 |
| **Total** | 21 | **23** | 22 | 22 |
| **Heavy three only** | **14** | 8 | 11 | 10 |
| **Weighted read** | strong output, poor fit | cheap, weak output | good all-round, privacy risk | surprisingly close |

*\*DIY tested hands-on across two models with a goal-rich brief; privacy scored after checking our existing plan terms.*

**Dimensions I weighted heaviest:** capability fit and brand-voice/brand-safety (it's a copywriting tool — on-brand output *is* the job) and data & privacy (a training-on-your-inputs clause is a real risk for brand copy).

**Read the two total rows against each other.** CopyFlow wins the raw total (23) and comes *last* on the heavy three (8). Penmark is the reverse — 21 overall, 14 on what matters. If you let the raw total decide, you buy the tool that is cheapest and easiest at exactly the thing you are not trying to optimise.

## The call

**Winner: the DIY baseline — "buy nothing new," for now.**

With a goal-rich brief, a general model already produces on-brand copy close to BrandForge on everyday pieces, at ~no marginal cost. None of the three specialized tools clearly *beats the baseline enough to justify its cost and risk*:

- **Penmark** — best output and tightest voice control, and it tops the heavy three (14). But copy-paste-only, premium-priced, and no claims-checking or compliance step: it writes an unsupported claim beautifully. The quality gap over a well-briefed general model is too small to justify the price and workflow friction.
- **CopyFlow** — cheap and well-integrated, but generic output means more editing and tone drifts across a batch; its banned-words filter catches wording, not claims. It's solving a problem the baseline already handles.
- **BrandForge** — the closest call; strongest on brand-voice/safety (the only compliance-approval workflow with an audit trail) and well-integrated, but the standard plan may train on your inputs, and the no-training tier costs *more than Penmark*. That pushes it to **pilot-only**, not adopt.

## Tradeoff accepted

The baseline loses on two things. **Stack integration** (no native CMS/scheduler — copy-paste), acceptable at current volume. And **brand-safety tooling** — no guardrails, no audit trail; our brand rules are enforced by the brief and a human read, not by the product. That is fine for everyday marketing copy and *not* fine the moment we make claims that need an approval record. If copy volume outgrows copy-paste, or a claims-approval trail becomes a requirement, revisit **BrandForge (no-training tier)** as the first upgrade.

## Recommendation memo (the deliverable)

> **Recommendation:** Don't buy a new copywriting tool yet. A goal-rich brief plus the general model we already pay for covers our needs at no added cost and no new data risk — checked, and our current business tier does not train on inputs. **Tradeoffs:** manual copy-paste (no integration), and no brand-safety guardrails or audit trail — brand rules ride on the brief plus a human read. **If volume grows** past what copy-paste can sustain, or we start making claims that need an approval record, pilot BrandForge on its no-training tier — never the standard tier, given the input-training clause. **Call: adopt the baseline now; revisit in one quarter.**

## Common mistakes

- Letting the highest total score win automatically (CopyFlow tops the raw total at 23 and comes last on the heavy three at 8) instead of weighing cost/fit/risk.
- Not scoring the **baseline**, so "buy nothing" never gets considered.
- Missing BrandForge's training-clause → price flip (the no-training tier costs more than Penmark).
- Treating brand-voice and brand-safety as one thing. Penmark locks voice tightly and checks claims not at all — a 4 that hides a real gap. Read the finding, not just the number.
- Skipping the DIY baseline's "check your existing terms" step and scoring its privacy as unknown, when it's a fact you can go and establish.
