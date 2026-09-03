# Demo Output — Score One Tool Against the Framework

*Actual Claude output — the framework applied to one copywriting tool, then a build-vs-buy check. One run; outputs vary.*

**Tool scored:** a specialized AI copywriting tool ("Penmark"-style: best-in-class output, standalone web app, premium price, does not train on your inputs). Scale 1 (poor) – 5 (excellent).

| Dimension | Score | Reasoning |
|---|---|---|
| Capability fit | 5 | Sharp, rarely generic, and consistent run to run on our real task. |
| Brand-voice control / brand-safety | 4 | Holds a defined brand voice once trained on samples, with no drift across a batch — for a copywriting tool that on-brand quality is most of the job. A 4, not a 5: we checked voice control and never checked brand-safety (no prohibited-claims list or compliance step confirmed), so the score rests on voice alone. |
| Fit with your stack | 2 | Standalone web app, no integrations — everything is copy-paste in and out. |
| Cost vs. value | 2 | Most expensive option; you're paying up for output quality and giving up integration. |
| Data & privacy | 5 | Does not use your inputs to train its models; clear terms. |
| Learning curve / adoption | 3 | Easy to learn, but the manual copy-paste workflow adds friction at scale. |

**Stress-testing a score (with Claude):** *"I gave fit with our stack a 2 — am I being too generous, given we'd copy-paste every draft?"* → No — a 2 is right; at volume, copy-paste is a real tax, not a rounding error.

**Build-vs-buy check:** running the same brief through a general model produced copy close to this tool's on everyday pieces, at ~no marginal cost. The tool's edge shows mainly on the highest-stakes pieces.

**Verdict:** **Pilot, not adopt.** Excellent output, but weak fit with our stack + premium price mean it must clearly beat the general model we already pay for — and on everyday copy it doesn't. Pilot it only for high-stakes, brand-critical pieces.

*The value isn't the total — it's this documented reasoning you can hand a skeptical manager.*

**Scaling to four options.** The exercise runs this same pass across three tools and a DIY baseline, and at four columns the Reasoning column no longer fits — so it moves rather than disappears: scores stay in the grid, the *why* becomes a short findings note below it (one bullet per option), and the memo carries the call.

| Dimension | Tool A | Tool B | Tool C | DIY baseline |
|---|---|---|---|---|
| Capability fit | … | … | … | … |
| Brand-voice control / brand-safety | … | … | … | … |
| Fit with your stack | … | … | … | … |
| Cost vs. value | … | … | … | … |
| Data & privacy | … | … | … | … |
| Learning curve / adoption | … | … | … | … |
| **Total** | … | … | … | … |

*Shape only, no scores — the same documented reasoning as above, relocated so four options fit on a page.*
