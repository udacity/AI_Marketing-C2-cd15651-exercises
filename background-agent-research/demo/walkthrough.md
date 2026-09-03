# Worked Demo — Delegate the Research, Then Audit What Comes Back

*The real content: the finished walkthrough the demo produces.*

> **Author/recorder note — read before you record.**
> This demo runs on the **same CMO request as the exercise**, and that is deliberate: the authoring outline specifies the shared scenario. The separation between demo and exercise is **depth, not scenario** — the demo audits **three** claims and stops. Two hard limits:
> 1. **Don't audit the market-size / growth-rate claim.** The returned brief will contain one. Opening it on camera hands over the exercise's entire finding. Name it as one for their audit and move on.
> 2. **Don't audit competitor list pricing.** That's the exercise's straightforward Trust win — leave it to them.
>
> The three claims below stay clear of both. Claims 1 and 2 were verified against the linked primary sources on **2026-09-04**; re-open every link at record time, because this module runs on live pages and they move. Claim 3 is the unattributed-roundup *pattern* rather than a specific page — which is the point of it — so audit whatever equivalent your run actually returns.

## Delegating is goals-not-steps with autonomy

Start from the CMO's request in [`research-task-brief.md`](../exercise/starter/research-task-brief.md) — competitive landscape and market trends for the water bottle market, premium reusable brands plus smart/hydration-tracking entrants — and turn it into a clear brief for a **Claude Code subagent**: a helper with its own instructions and web-research tools, defined in `.claude/agents/`, that runs in the background and hands back a finished brief.

You are not writing steps. You write four things, then get out of the way:

- **The question** — exactly what to answer, and what it's for (Vessl's launch positioning and pricing).
- **The scope** — which brands, and which dimensions: positioning, pricing, app or subscription model, standout features, gaps, plus category trends.
- **The output format** — a short brief with a source, and the date it was retrieved, for every claim.
- **The guardrails** — prefer credible and current sources; flag anything it can't verify; stop when the scope is covered.

One guardrail earns its place in a competitive brief: **make the agent name who is asserting each claim**, and keep a brand's own word separate from an independent one. Only your delegation brief can force that distinction, and it's the distinction the audit turns on.

## Let it run, then read once for usefulness

Set the subagent running and let it work autonomously. When it comes back, read the brief once to see whether it's useful — the shape, the coverage, whether it answered the question you asked. An autonomous agent always hands back a confident, complete-looking brief. **Completeness is not credibility.** Nothing in a well-formatted brief tells you whether its sources exist.

## The audit is the real work

Pick three key claims and open the cited sources. For each, run the four checks: is the source **real**, is it **credible for this claim**, is it **current** — record the date you opened it, so anyone reading the audit can tell how fresh the check is — and does it **support the claim as the brief words it**?

Three claims, and between them the whole verdict range:

- **One that holds up.** LARQ frames its Bottle PureVis on water quality rather than intake: PureVis technology "to clean your water and bottle at the touch of a button," eliminating "up to 99%\* of bio-contaminants such as E. coli," with no hydration tracking anywhere in the product FAQ. Opened on LARQ's own support page: real, primary, current, and it says exactly that. **Trust** — for exactly what it proves. This is evidence of how LARQ *positions* the product, not proof the purification performs as advertised. Note the asterisk on "up to 99%" and keep the wording matched to it.
- **One that's half-right.** The brief says "HidrateSpark's companion app is free — no subscription." The sourcing looks impeccable: the brand's own app page plus the iOS App Store listing, both current. **Supported** is where it breaks. The download is free, but the listing reads "Free · In-App Purchases," and HidrateSpark PREMIUM is sold as a monthly and annual subscription with a one-month free trial. Real, credible, current — one check down. **Verify-first**, and re-word it before it informs a pricing call: a competitor with a free app *and* a paid tier is a different pricing landscape from one giving everything away.
- **One that has to go.** "Smart and tracking bottles are about 15% of premium bottle sales," cited to a glossy "best smart water bottles of 2026" roundup. The page opens, so **real** passes — and that's all that does. No author, no masthead, no publisher, the same paragraphs running verbatim across sibling domains, and the figure attributed to "industry data suggests" and nothing further. Not credible for a market-share number, and unsupported in any checkable sense: two checks down. **Drop.**

The middle claim is the demo's real lesson. A primary source and a wrong claim can sit in the same sentence. The agent didn't invent anything; it compressed. **Auditing the source list instead of the sources would have waved it straight through** — the only thing that catches it is opening the page and reading it against the brief's exact wording.

## Mark up the brief

Per claim, one of three verdicts, decided by the four checks:

- **Trust** — all four checks pass (real, credible for the claim — primary or clearly attributed, current as of the date you recorded, supported when you open it). Safe to cite as a fact.
- **Verify-first** — the checks are mixed. Usable as directional; confirm it against a primary source, or re-word it to what the source actually says, before you cite it as a number.
- **Drop** — two or more checks fail, or no source can be identified at all. Don't cite it: replace the source or cut the claim.

Then say what you'd do with each one. A dropped claim is not a claim you've disproved — a citation that doesn't hold up tells you nothing about whether the underlying point is true. It tells you that you can't say it yet. Re-source it or cut it; don't re-word it and keep it.

Three claims took a few minutes. The same four checks run down the rest of the brief.

You own the brief you pass on, not the agent.

## Key takeaway

A background agent can do hours of research in minutes, but a polished brief is a starting point, not a source of truth. Delegating well and auditing hard is what makes the output usable — and the claim that catches you out won't be the obviously shaky one, it'll be the one with a real source behind a slightly wrong sentence.
