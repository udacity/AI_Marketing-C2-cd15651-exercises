# Delegate, Then Audit a Creator Shortlist

Vessl is leading its launch with creators rather than ads, and the CMO wants a vetted shortlist before outreach. Delegate the research to a background agent, then audit what comes back for source quality and write a verdict you'd put budget behind. Creator numbers are some of the least reliable numbers in marketing, so the audit is the real work here.

Work with a **Claude Code subagent**, a helper Claude Code runs in the background with its own instructions and web-research tools, which hands back a finished shortlist. (This is the Claude Code feature, not the Anthropic API "Managed Agents" or the Agent SDK, which are separate developer products.) You can brief the agent inline; a ready-made definition is provided if you'd rather reuse one. Use:

- [`influencer-research-brief.md`](influencer-research-brief.md), the CMO's raw request to scope.
- [`source-quality-audit-checklist.md`](source-quality-audit-checklist.md), the checklist for auditing the returned shortlist.
- [`market-researcher-subagent.md`](market-researcher-subagent.md), optional: a ready-made subagent definition and how to install it (`.claude/agents/market-researcher.md`).

**Before you start:** both halves of this exercise need live web access, the agent researches on the web, and you audit by opening its sources yourself. Claude Code will ask permission the first time it visits each new site; approving as you go is normal. This research surfaces real, named creators whose metrics change over time, so treat every number as a claim to check, not a fact.

## What to produce

- The agent delegation brief you wrote (question, scope, output format, guardrails).
- The creator shortlist the agent returned.
- A source-quality audit note as a table: creator | claim (reach / engagement / audience / cost) | cited source | who asserts it (creator's own vs. independent) | accessed (date) | credible? | verified against source? | trust / verify-first / drop.
- A scope-coverage check: which of the CMO's asks the shortlist actually answered per creator, and which came back thin.
- A two-line verdict: which creators are ready to advance to outreach as-is, and what must be verified before you commit budget.

## Requirements

- Scope the delegation before you run it: state the question, the scope, the output format (a claim-by-claim shortlist with sources), and the guardrails (credible and recent sources, keep self-reported figures separate from independent ones, flag the unverifiable, define "done"). A vague request gets a vague list.
- Audit real sources, not just the shortlist's confidence. A creator's own follower count or media-kit reach is a **claim**, not a fact. Check it against an independent source, the live platform profile, or a third-party tool like Social Blade (follower-growth history), HypeAuditor, or Modash, and treat a sudden follower spike or an engagement rate that disagrees across tools as a red flag.
- Record the date you accessed each source. Reach and rates change, and an undated claim gives the CMO no way to judge how current it is.
- Reach a per-claim verdict, trust, verify-first, or drop, using the rule in the checklist, not a general impression. Self-reported reach with no independent backing is verify-first at best.
- Audit the delegation too, not only the claims. Source quality tells you whether a creator's numbers are trustworthy; it tells you nothing about whether the shortlist answered the CMO's whole request. Read the request line by line against what came back. Engagement authenticity, brand-safety, and real rates are the asks most likely to come back thin, and those are exactly the ones budget rides on.
- Remember you own the shortlist you pass on. The two-line verdict should reflect who you'd stake budget on.

## Done when

You scoped the delegation in writing before running it, your audit note reaches a defensible verdict on each key claim, you can say which of the CMO's asks came back thin, and your two-line summary tells the CMO which creators are ready for outreach and what still needs checking before any budget is committed.
