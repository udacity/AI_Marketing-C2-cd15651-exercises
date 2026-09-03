# Worked Demo — Delegate the Research, Then Audit What Comes Back

*The real content: the finished walkthrough the demo produces.*

## Delegating is goals-not-steps with autonomy

Start from the CMO's request in [`research-task-brief.md`](../exercise/starter/research-task-brief.md) (competitive landscape + market trends for the water bottle market, with premium reusable brands and smart/tracking entrants as one segment to watch) and write it into a clear brief for a **Claude Code subagent**:

- **The question** — exactly what to answer.
- **The scope** — which competitors, and what dimensions (positioning, pricing, features, market trends).
- **The output format** — a short brief with a source, and the date it was retrieved, for every claim.
- **The guardrails** — prefer credible and recent sources, flag anything it can't verify, stop when the brief is covered.

## Let it run, then read once for usefulness

Set the subagent running and let it work autonomously. When it returns, read the brief once to see whether it's useful. An autonomous agent always returns a confident, complete-looking brief — but completeness is not credibility.

## The audit is the real work

Pick three key claims and open the cited sources. For each, run the four checks: is the source real, is it credible for this claim, is it current — note the date you opened it, so anyone reading the audit can tell how fresh the check is — and does it actually support the claim?

- **One that holds up:** a pricing or market figure backed by a primary, current source that says exactly that. Trust it.
- **One that's weak** *(illustrative — the actual weak claim depends on what the agent returns)*: a confident statistic with a vague "studies show," a dead citation, or a real source used to back a claim it never makes. Verify-first — usable as a direction, not as a number.
- **One that has to go:** a stat sitting on a page that looks like a source until you open it — a polished, recent-looking "best smart bottles of 2026" listicle with no author, no publisher, the same text mirrored across sibling domains, and no attribution behind its numbers. Real fails and credible fails: drop it.

## Mark up the brief

Per claim, one of three verdicts, decided by the four checks:

- **Trust** — all four checks pass (real, credible for the claim — primary or clearly attributed, current as of the date you recorded, supported when you open it). Safe to cite as a fact.
- **Verify-first** — the checks are mixed. Usable as directional; confirm it against a primary source before you cite it as a number.
- **Drop** — two or more checks fail, or no source can be identified at all. Don't cite it: replace the source or cut the claim.

You own the brief you pass on, not the agent.

## Key takeaway

A background agent can do hours of research in minutes, but a polished brief is a starting point, not a source of truth. Delegating well and auditing hard is what makes the output usable.
