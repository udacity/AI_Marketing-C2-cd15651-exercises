# Demo Output — Score One Tool Against the Framework

*Actual Claude output — the framework applied to one AI copywriting tool, then a build-vs-buy check. One run; outputs vary.*

**Tool scored:** **Draftwell**, an AI copywriting tool built for email — it sits inside your sending platform, learns a voice from your past sends, and drafts subject lines, promo copy and newsletter bodies against it. **The real task:** our recurring email programme — one newsletter a week, a six-email welcome sequence, two promo sends a month, about 20 pieces of copy a month, written today by one person against a one-page voice guide. Scale 1 (poor) – 5 (excellent).

| Dimension | Score | Reasoning |
|---|---|---|
| Capability fit | 3 | Ran the last two months of real sends through the trial — 41 pieces. Subject lines and short promo sends came back shippable. The ~400-word newsletter body came back competent and structurally flat; about half were reordered by hand before sending. Strong on short form, mediocre on the long piece — and the long piece is where the programme's clicks come from. |
| Brand-voice control / brand-safety | 3 | Zero avoid-list violations across all 41, and no drift at all — tone at piece 41 matched piece 1. But read the batch, not the sample: every email opens on the same rhetorical move and closes on the same cadence. Nothing is off-brand; the brand starts sounding automated. Sameness isn't a capability failure — each draft is fine alone — it's a voice finding, because voice is a property of the batch. No claims check either: it asks whether a sentence is on tone, never whether it's true. |
| Fit with your stack | 5 | Runs inside the email platform we already send from. Drafts arrive as real drafts in the ESP and edits there flow back, so no second copy goes stale in a second tool. It only does email, which costs us nothing because our job is only email — the same limit would be a 2 if we were buying it for landing pages too. |
| Cost vs. value | 3 | Unlimited seats, priced per thousand subscribers — the meter runs on the list, not the team. Under $100/mo today, but this year's plan roughly triples the list and so triples the bill: the meter points at the number we're trying to grow. Scored at the volume we're committing to, and against a near-free baseline rather than against zero. |
| Data & privacy | 4 | No training on inputs, on every tier, in the contract rather than the FAQ — better terms than most. What it costs is footprint: to personalise it ingests twelve months of past sends plus the subscriber segments, so far more customer data sits with the vendor than with a tool that only ever sees a brief. Default retention 24 months, no shorter option. Exportable at any time. Good terms, bigger blast radius. |
| Learning curve / adoption | 2 | A migration, not a signup. Twelve months of past sends imported and tagged before the voice model is worth anything, and the ESP connector is configured by their team on their calendar. Three to four weeks to a first usable draft, all of it landing on the one person who is also still writing the copy that month. |
| **Total** | **20** | |

**Stress-testing a score (with Claude):** *"I gave cost vs. value a 4 because it's under $100 a month at our list size — am I being too generous?"* → Yes, twice. You scored this month's invoice for a meter that runs on list growth, and you called it cheap without having tested the baseline it's supposed to be cheap *against*. **Scored 4 at first; it's a 3.** Scores are meant to move when argued with — and the second half of that answer is why the next check exists.

**Build-vs-buy check:** the same 20 pieces and the same voice guide, written up as a brief file and run through two general models we already pay for. On the copy the baseline wins — given the brief, the newsletter bodies came back better structured than Draftwell's, and the short pieces were a tie. On everything around the copy it loses: nothing is remembered between sessions, so the brief gets re-pasted and a person, not the tool, holds the voice across twenty pieces; and nothing lands in the send tool, so every piece is a copy-paste and the two versions diverge the moment one is edited. **The baseline wins on the copy and loses on the plumbing** — which turns the buying question into "are we paying for writing, or for a sync?"

**Decision size:** the expensive door is the one on the way *in*. Leaving is easy — the copy lives in the ESP as drafts we own, cancel with a month's notice. Entering costs three to four weeks of import, tagging and vendor-side setup you don't get back. That shape changes the remedy: you de-risk it by making the entry smaller, not by reviewing the contract harder. Durability: two years old, and the integration is built on a single ESP's API, so its future rides on a partnership as well as its funding — which matters here because the setup cost is paid up front.

**Verdict:** **Pilot, one stream only** — the weekly newsletter, migrated with that archive and nothing else. Six issues, six weeks, days of setup instead of weeks. *Not a pass,* because we scored a cold tool and the two dragging scores (capability 3, brand-voice 3) are exactly what the vendor's "it gets good once it's fed" claim is about. *Not an adopt,* because the only way to test that claim is to pay the expensive part of owning it, so we buy the smallest version that can still answer the question. **Kill criterion, agreed up front:** if by issue six the bodies still get reordered by hand, or the six read as one email written six times, we stop — we were only buying the sync, and there are cheaper syncs. **Tradeoff accepted:** a 2 on adoption, taken knowingly — spending the copywriter's month to buy information.

*The value isn't the total — it's this documented reasoning you can hand a skeptical manager.*

**Scaling to more options.** At four columns the Reasoning column no longer fits on a page — so it moves rather than disappears: scores stay in the grid, the *why* becomes a short findings note below it (one bullet per option), and the memo carries the call.

| Dimension | Option 1 | Option 2 | Option 3 | DIY baseline |
|---|---|---|---|---|
| Capability fit | … | … | … | … |
| Brand-voice control / brand-safety | … | … | … | … |
| Fit with your stack | … | … | … | … |
| Cost vs. value | … | … | … | … |
| Data & privacy | … | … | … | … |
| Learning curve / adoption | … | … | … | … |
| **Total** | … | … | … | … |

*Shape only, no scores — the same documented reasoning as above, relocated so four options fit on a page.*
