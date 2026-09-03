# Worked Demo — Delegate the Research, Then Audit What Comes Back

*The real content: the finished walkthrough the demo produces.*

> **Author/recorder note.** The claims and citations in [`example-output.md`](example-output.md) are **illustrative placeholders, not verified findings** — brands are written as `[Brand A]`-style stand-ins and no URLs are given. This module runs on live web sources: do the run on camera and audit whatever it actually returns, then replace `example-output.md` with your real output and real, re-verified links. Keep the shape if the run supports it (one Trust, two Verify-firsts, one Drop); never read a placeholder figure out as a fact.

## Delegating is goals-not-steps with autonomy

Start from the Head of Brand's request in [`sustainability-claims-research-request.md`](sustainability-claims-research-request.md) — which sustainability claims the premium reusable-bottle category is already making, and how much of each one is actually backed — and turn it into a clear brief for a **Claude Code subagent**: a helper with its own instructions and web-research tools, defined in `.claude/agents/`, that runs in the background and hands back a finished brief.

- **The question** — exactly what to answer.
- **The scope** — which brands, and which dimensions: material claims, packaging claims, third-party certification, consumer research.
- **The output format** — a short brief with a source, and the date it was retrieved, for every claim.
- **The guardrails** — prefer primary and current sources; keep a brand's own claim separate from an independently certified one; flag anything it can't verify; stop when the brief is covered.

One guardrail earns its place in a claims audit: **make the agent name who is asserting each claim.** "The category is going plastic-free" and "two named brands announced a switch" are different claims, and only your delegation brief can force the agent to keep them apart.

## Let it run, then read once for usefulness

Set the subagent running and let it work autonomously. When it returns, read the brief once to see whether it's useful. An autonomous agent always hands back a confident, complete-looking brief — but completeness is not credibility.

## The audit is the real work

Take the key claims and open the cited sources. For each, run the four checks: is the source real, is it credible **for this claim**, is it current — note the date you opened it, so anyone reading the audit can tell how fresh the check is — and does it actually support the claim *as the brief words it*?

Sustainability copy is where the "credible for this claim" check bites:

- **One that holds up:** a brand's own sustainability page plus that brand's live entry in the certifying body's public directory. Primary for what the brand claims, independent for the certificate. Trust it — for exactly that: they make this claim, and the certificate is real. It is not proof the material claim itself was independently audited.
- **One that's stale:** a real trade-press piece that says precisely what the brief says — reported two years ago. Packaging programs slip and get re-announced. Verify-first: confirm it actually shipped before you tell anyone the category has moved.
- **One where the number drifts:** a named research firm's own survey, real and current, but its question was about "sustainable products" globally across categories, and the brief has quietly re-labelled it as packaging in this one. Verify-first: a direction, not a number for a slide.
- **One that has to go:** the most specific-looking citation in the brief — a titled, year-stamped industry white paper — whose link 404s and whose title returns nothing anywhere, under any publisher. **Real** fails, and **supported** can't even be run. Drop it.

## Mark up the brief

Per claim, one of three verdicts, decided by the four checks:

- **Trust** — all four checks pass (real, credible for the claim — primary or clearly attributed, current as of the date you recorded, supported when you open it). Safe to cite as a fact.
- **Verify-first** — the checks are mixed. Usable as directional; confirm it against a primary source before you cite it as a number.
- **Drop** — two or more checks fail, or no source can be identified at all. Don't cite it: replace the source or cut the claim.

Then say what you'd do with each one. A dropped claim is not a claim you've disproved — a citation that doesn't exist tells you nothing about whether the underlying point is true. It tells you that you can't say it yet. Re-source it or cut it; don't re-word it and keep it.

You own the brief you pass on, not the agent.

## Key takeaway

A background agent can do hours of research in minutes, but a polished brief is a starting point, not a source of truth. Delegating well and auditing hard is what makes the output usable — and in claims-heavy copy, "who asserts this, and who checked them" *is* the audit.
