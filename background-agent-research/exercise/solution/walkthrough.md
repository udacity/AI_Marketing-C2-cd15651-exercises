# Solution: Delegate, Then Audit a Creator Shortlist

*Worked solution, one strong example. The returned shortlist and its sources are illustrative of what an agent produces and how to audit it; a student's run pulls live sources and real, named creators, so the specific names and numbers will differ. What matters: a well-scoped delegation, a claim-by-claim source audit that separates self-reported reach from independent, and a defensible verdict.*

## 1. The delegation brief (what I handed the agent)

> **Question:** Build a vetted shortlist of real creators Vessl could sponsor for a creator-led launch of a smart hydration bottle.
> **Scope:** creators across hydration/wellness, fitness, health and fitness-tech reviews, sustainability, and everyday lifestyle. Per creator: name and platform(s), audience size and demographics, engagement rate, content style and values, brand-safety flags, rough sponsorship cost.
> **Output format:** a claim-by-claim shortlist; **every meaningful claim (reach, engagement, demographics, cost) carries a source, the date it was published, and a link, and names who is asserting it** (the creator's own numbers vs. an independent source).
> **Guardrails:** keep self-reported figures separate from independent ones; prefer third-party audience-quality data over follower counts alone; flag anything unverifiable; stop when scope is covered.

## 2. Read once for usefulness

The returned shortlist looked thorough: named creators grouped by category, follower counts, engagement figures, a few cost estimates. **Completeness is not credibility**, and with creators it is especially not, so it goes straight to audit.

## 3. Source-quality audit (illustrative)

The verdict follows the rule in [`source-quality-audit-checklist.md`](../starter/source-quality-audit-checklist.md): **Trust** when all four checks pass (real, credible for the claim, current as of the date recorded, supported when you open it); **Verify-first** when the checks are mixed (usable as directional, confirm against an independent source before you rely on it); **Drop** when two or more checks fail or no source can be identified. With creators, the check that does the most work is *who is asserting it*, a follower count on the creator's own profile or media kit is self-reported, and self-reported reach is a claim, not a measurement.

| Creator | Claim | Cited source | Who asserts | Accessed | Credible? | Verified? | Verdict |
|---|---|---|---|---|---|---|---|
| Fitness creator A | ~1.2M followers | The creator's live platform profile | Platform (independent-ish) | 2026-09-26 | Yes | Yes, the count is on the live profile | **Trust** (for reach only) |
| Fitness creator A | 8% engagement rate | Creator's media kit | Creator (self-reported) | 2026-09-26 | Mixed, no independent backing | Third-party tool shows ~1.9% | **Verify-first** → the self-reported figure is ~4x the independent one |
| Lifestyle creator B | 16M reach | Creator bio / press blurb | Creator (self-reported) | 2026-09-26 | No, an independent tool reports ~2M | No, self-reported and independent disagree by ~8x | **Drop** the 16M figure; use the ~2M and re-verify |
| Gadget reviewer C | ~$25–40k per sponsored video | "Industry estimate," no rate card | Unnamed aggregator | 2026-09-26 | No source to open | No | **Drop** as a number; treat as a placeholder until a rate card or quote confirms it |
| Sustainability creator D | Credible values fit (press coverage) | Named outlets (e.g., major magazine/newspaper features) | Independent | 2026-09-26 | Yes, named reputable outlets | Yes, articles exist and say so | **Trust** |

The engagement-rate row is the interesting call, and it is the creator equivalent of the demo's half-right claim: the reach can be real and verifiable while the engagement number, self-reported in a media kit, is inflated. Only opening an independent tool catches it. A follower graph with a sudden vertical spike (visible in Social Blade) is the other classic tell, bought followers, and it turns a large reach into a **Drop** for authenticity even when the raw count is technically "real."

## 4. Scope-coverage check

The audit says which numbers are trustworthy. It says nothing about whether the shortlist answered the CMO, so read the request back, ask by ask: who they are, audience size and fit, engagement authenticity, content style and values, brand-safety flags, rough cost.

Typically, **name, platform, and follower counts come back well**, **content/values comes back reasonably**, and the three asks that actually gate a budget decision, **engagement authenticity, brand-safety, and real cost**, come back thinnest. An agent will happily list a creator's follower count and leave "is this audience real?" and "what would this cost?" as the exact gaps that matter most. Split the CMO's asks your own way before you read the return, then hold the shortlist to your list, a scope defined after seeing the answer always looks satisfied.

That gap is invisible in the verdict column by construction: every check interrogates a claim that is there, none can flag a claim that isn't. Auditing sourcing without auditing coverage is how a shortlist of impressive follower counts gets forwarded as a vetted recommendation.

## 5. Two-line verdict (for the CMO)

> **Ready for outreach:** the creators whose reach checks out against an independent source and whose values fit, screened for brand-safety, a short list, deliberately.
> **Verify before we commit budget:** every self-reported engagement rate (confirm against a third-party tool first), any follower count that disagrees across sources, and all cost figures (get a rate card or quote, none were independently confirmed). No budget moves on a self-reported number.

## Common mistakes

- A vague delegation ("find us some influencers") → a vague list of big names with no vetting.
- Trusting a follower count because it is large and on the profile, without checking engagement authenticity or growth history.
- Treating a media-kit engagement rate as a fact instead of a self-reported claim.
- Softening a Drop to Verify-first because the creator is famous. If a cost figure names no source, "industry estimate" is a Drop, not a number.
- No access date, so nobody can tell whether the reach check is still good next month.
- Auditing only the numbers that came back and missing that brand-safety, engagement authenticity, and cost, the asks budget rides on, were never answered.
