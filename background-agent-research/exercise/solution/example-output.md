# Sample Output — Delegate, Then Audit

*Actual Claude output — a real web-sourced research run against the CMO's request, then a source-quality audit. One run; live sources change over time.*

*These sources were captured 2026-09-01 to 2026-09-03. Prices and market-size figures move, so if you open them today and find different numbers, that's expected — not a mistake in your audit.*

## Delegation brief given to the agent

> **Q:** competitive landscape + market trends for the water bottle market (premium reusable brands plus smart/tracking entrants as one segment), for Vessl's launch positioning + pricing.
> **Scope:** 3–5 key players (premium reusable + smart entrants) — positioning, target, rough pricing, app/subscription, standout features, gaps; plus category trends.
> **Output:** short brief, a source (link + date retrieved) for every meaningful claim.
> **Guardrails:** credible + recent sources; flag anything unverifiable; stop when scope is covered.

## Returned brief (excerpt the learner audits)

> 1. Premium reusable bottles cluster ~**$29–$55** (Hydro Flask 18oz ~$29 → 40oz ~$55; Owala FreeSip 32oz ~$35). *(Owala + Hydro Flask own product pages — accessed 2026-09-01)*
> 2. **HidrateSpark PRO** (smart/tracking) lists **~$70–$85** — a clear tracking premium; pairs with a companion app. *(HidrateSpark store, Apple, Amazon — accessed 2026-09-01)*
> 3. The smart water bottle market is **growing ~12% CAGR**. *(four market-research firms — accessed 2026-09-02)*
> 4. "**Most consumers want hydration reminders.**" *(no source given — checked 2026-09-02, nothing to open)*
> 5. Wearables/health-tracking adoption is rising, pulling hydration into the quantified-self trend. *(market-research summaries — accessed 2026-09-03; no firm, report, or link named)*

## Source-quality audit note

Verdicts follow the rule in the checklist: **Trust** = all four checks pass (real, credible for the claim — primary or clearly attributed, current as of the date recorded, supported when you open it) — safe to cite as a fact; **Verify-first** = mixed checks — usable as directional, confirm against a primary source before citing it as a number; **Drop** = two or more checks fail, or no source can be identified.

| Claim | Cited source | Accessed | Credible? | Verified? | Verdict |
|---|---|---|---|---|---|
| 1. Reusable pricing $29–$55 | Owala + Hydro Flask own product pages | 2026-09-01 | Yes — the manufacturers themselves | Yes — prices match | **Trust** |
| 2. HidrateSpark ~$70–$85 | HidrateSpark store, Apple, Amazon | 2026-09-01 | Yes | Yes — list prices match | **Trust** |
| 3. "~12% CAGR" | 4 market-research firms | 2026-09-02 | Unclear — real firms, but incompatible scopes | Partly — the growth direction holds, but no firm gives ~12%; they give **7.49%–19.5%** and base sizes differ ~100× | **Verify-first** |
| 4. "Most consumers want reminders" | none / SEO phrasing | n/a — no source to open | No | No — opinion stated as data | **Drop** |
| 5. Wearables adoption rising | "market-research summaries" — no firm, report, or link named | 2026-09-03 — but to what? nothing identifiable to open | Unclear — can't assess an unnamed source | Couldn't check — no source to open | **Drop** |

**Why claim 5 is a Drop, not a Verify-first.** The trend is almost certainly real — that's what makes it tempting. But "market-research summaries" names no firm, no report, and no link, so there is no usable source to identify, and the rule is explicit: that alone is a **Drop**. Verify-first is for a claim whose *source* you can open and whose checks come back mixed; here there's nothing to open, so three of the four checks can't even be run. A claim can be directionally true and still have to be dropped for want of a citable source. If you want the trend in the deck, re-source it to a named report and re-audit it as a new claim — don't launder it through a softer verdict.

## Scope-coverage check

Every claim above was audited for sourcing, and two survived. That still doesn't tell us whether the agent answered the CMO's question. Read the request line by line against what came back:

| The CMO asked for | Came back? |
|---|---|
| Key players (premium reusable + smart entrants) | **Yes** — Hydro Flask, Owala, HidrateSpark |
| Pricing — roughly where they land | **Yes** — claims 1–2, both Trust |
| How they package it / any app or subscription | **Partial** — "pairs with a companion app," nothing on packaging or subscription pricing |
| Category trends | **Yes, but** — the only two claims carrying it are the Verify-first and a Drop |
| Their positioning — how each frames itself | **No** |
| Who they target | **No** |
| Standout features — what they lead with | **No** |
| Obvious gaps in the category | **No** |

Four of the CMO's asks came back empty, one came back partial, and another arrived attached to claims that failed the audit. What survives is competitor pricing and the three brand names: genuinely useful, impeccably sourced, and a fraction of what was requested.

How many asks the request contains is a judgement call, not a fact — the CMO wrote prose, not a numbered list, and several of those bullets carry two asks apiece. Split it your own way; what matters is that you split it *before* reading the return, then hold the agent to your own list. A scope you define after seeing the answer will always look satisfied.

This is the failure the verdict column cannot show you. Every row in the audit table asks whether a claim is *trustworthy*; none of them asks whether the brief is *responsive*. An agent stops when it has written something confident and complete-looking, not when it has covered your scope — so the delegation needs auditing alongside the citations. Positioning, target, features and gaps were all in the delegation brief we handed the agent; they have to be asked for again, specifically.

## Two-line verdict

> **Act on as-is:** competitor pricing only — claims 1–2, from the manufacturers' own pages, checked Sept 1 — which is two of five claims and a fraction of what you asked for.
>
> **Verify or cut before it reaches you:** the "~12% CAGR" needs one clearly-scoped source (reputable firms disagree by an order of magnitude), and claims 4 and 5 are dropped — opinion dressed as data, and a trend I'd bet is true with nothing citable behind it — until they're re-sourced to a named report.

Two lines, because that is the deliverable: one on what's ready to act on, one on what has to be checked first. Anything longer is the audit table again, and the CMO already has that.

**Sources** (date accessed in brackets)**:** [Owala FreeSip](https://owalalife.com/products/freesip) [2026-09-01] · [Hydro Flask bottles (manufacturer)](https://www.hydroflask.com/shop/bottles) [2026-09-01] · [HidrateSpark](https://hidratespark.com/collections/products) [2026-09-01] · [Fortune Business Insights](https://www.fortunebusinessinsights.com/smart-water-bottle-market-115917) [2026-09-02] · [MarketResearchFuture](https://www.marketresearchfuture.com/reports/smart-water-bottle-market-21726) [2026-09-02] · [market.us](https://market.us/report/smart-water-bottle-market/) [2026-09-02] · [ResearchNester](https://www.researchnester.com/reports/smart-bottles-market/6524) [2026-09-02]
