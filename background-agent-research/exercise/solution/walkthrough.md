# Solution — Delegate, Then Audit for Source Quality

*Worked solution — one strong example. The returned brief and its sources are illustrative of what an agent produces and how to audit it; a student's run will differ. What matters: a well-scoped delegation, a claim-by-claim source audit, and a defensible verdict. (A real background-agent run pulls live sources — treat the citations below as a worked illustration of the audit method.)*

## 1. The delegation brief (what I handed the agent)

> **Question:** Competitive landscape + market trends for the water bottle market (premium reusable brands plus smart/tracking entrants as one segment), to inform Vessl's launch positioning and pricing.
> **Scope:** 3–5 relevant brands (premium reusable + smart/tracking entrants). For each: positioning, target, rough pricing, app/subscription model, standout features, obvious gaps. Plus 3–4 category trends (hydration, wearables, health-tracking).
> **Output format:** a short brief; **every meaningful claim carries a source (link + date retrieved).**
> **Guardrails:** prefer credible, recent sources; flag anything you can't verify; don't pad; stop when the scope is covered.

## 2. Read once for usefulness

The returned brief was well-organized and complete-looking — competitors, a pricing table, a trends section. **Completeness is not credibility**, so it goes straight to audit.

## 3. Source-quality audit (illustrative)

The verdict isn't a vibe — it follows the rule in [`source-quality-audit-checklist.md`](../starter/source-quality-audit-checklist.md): **Trust** when all four checks pass (real, credible for the claim — primary or clearly attributed, current as of the date recorded, and supported when you open it) — safe to cite as a fact; **Verify-first** when the checks are mixed — usable as directional, confirm against a primary source before citing it as a number; **Drop** when two or more checks fail, or no source can be identified. The **Accessed** date is what makes the "current?" check answerable — and what tells the CMO how fresh this audit is.

| Claim | Cited source | Accessed | Credible? | Verified against source? | Verdict |
|---|---|---|---|---|---|
| Reusable pricing ~$29–55 (Hydro Flask, Owala) | Hydro Flask + Owala own product pages | 2026-09-01 | Yes — the manufacturers themselves | Yes — prices match | **Trust** |
| HidrateSpark PRO ~$70–85 (smart entrant) | HidrateSpark store, Apple, Amazon | 2026-09-01 | Yes | Yes | **Trust** |
| "Smart bottle market ~12% CAGR" | Four research firms | 2026-09-02 | Unclear — real firms, but incompatible scopes | Partly — the growth direction holds, ~12% isn't in any one of them (they range 7.49%–19.5%, base sizes ~100× apart) | **Verify-first** |
| "Most consumers want hydration reminders" | None — SEO phrasing, no source given | n/a — no source to open | No | No — nothing to open; opinion stated as data | **Drop** |
| Wearables/health-tracking adoption rising | "Research summaries" — no firm, report, or link named | 2026-09-03 — nothing identifiable to open | Unclear — can't assess an unnamed source | Couldn't check — no source to open | **Drop** |

The last one is the interesting call. The trend is almost certainly real, which is exactly why it's tempting to wave through as "directional." But "research summaries" names no firm, no report, no link — there's no usable source to identify, and the rule makes that a **Drop** on its own. Verify-first is for a claim whose source you can open and whose checks come back mixed; with nothing to open, three of the four checks can't be run at all. **A claim can be directionally true and still have to be dropped for want of a citable source.** Re-source it to a named report and audit it as a new claim.

## 4. Two-line verdict (for the CMO)

> Competitor pricing (reusable and smart), checked against the manufacturers' own pages on Sept 1, is solid and I'd act on it now. The "~12% CAGR" needs verifying first: reputable firms disagree by an order of magnitude, so I'd pick one clearly-scoped source or cut the number before it reaches the CMO. Two claims are dropped — "consumers want reminders" (SEO opinion, no source to open) and the wearables trend (a read I'd bet is right, cited to unnamed "research summaries") — and neither goes in the deck until it's re-sourced to a named report.

## Common mistakes

- A vague delegation ("research the market") → a vague, unsourced brief.
- Trusting the brief because it *looks* complete and confident.
- Auditing the writing instead of opening the actual sources.
- No per-claim verdict — "looks fine overall" isn't an audit.
- Softening a Drop to Verify-first because the claim *sounds* right. If you can't name a source to open, "directionally true" isn't a verdict — it's a Drop.
- No access date, so nobody — including you, next month — can tell whether the check is still good.
