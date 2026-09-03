# Delegate, Then Audit for Source Quality

The CMO wants a competitive-landscape and market-trends brief before Vessl locks its launch. Delegate the research to a background agent, then audit what comes back for source quality and write an audit note.

Work with a **Claude Code subagent** — a helper Claude Code runs in the background with its own instructions and web-research tools, which hands back a finished brief. (This is the Claude Code feature, not the Anthropic API "Managed Agents" or the Agent SDK, which are separate developer products.) Use:

- [`market-researcher-subagent.md`](market-researcher-subagent.md) — a ready-made subagent definition and how to install it (`.claude/agents/market-researcher.md`).
- [`research-task-brief.md`](research-task-brief.md) — the CMO's raw request to scope.
- [`source-quality-audit-checklist.md`](source-quality-audit-checklist.md) — the checklist for auditing the returned brief.

**Before you start:** both halves of this exercise need live web access — the agent researches on the web, and you audit by opening its sources yourself. Claude Code will ask permission the first time it visits each new site; approving as you go is normal, not a fault. And if you create `.claude/agents/` in a session that's already running, restart Claude Code so it picks the new subagent up.

## What to produce

- The agent delegation brief you wrote (question, scope, output format, guardrails).
- The research brief the agent returned.
- A source-quality audit note as a table: claim | cited source | accessed (date) | credible? | verified against source? | trust / verify-first / drop.
- A two-line verdict: how much of the brief you'd act on as-is, and what you'd verify before it goes to the CMO.

## Requirements

- Scope the delegation before running it: state the question, the scope, the output format (a claim-by-claim brief with sources), and the guardrails (credible and recent sources, flag the unverifiable, define "done"). A vague request gets a vague brief.
- Audit real sources, not just the brief's confidence. For each key claim, confirm the source is real and credible, current, and actually supports the claim.
- Record the date you accessed the source, claim by claim. Recency is part of whether you can cite something: a price or market figure you last opened weeks ago may already be wrong, and an undated claim gives the CMO no way to judge how current it is.
- Reach a per-claim verdict — trust, verify-first, or drop — using the rule in the checklist, not just a general impression.
- Remember you own the brief you pass on. The two-line verdict should reflect what you'd stake your name on.

## Done when

You scoped the delegation in writing before running it, your audit note reaches a defensible verdict on each key claim, and your two-line summary tells the CMO exactly how much of the brief is ready to act on and what still needs checking.
