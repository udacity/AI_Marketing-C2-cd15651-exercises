# Demo — Delegate the Research, Then Audit What Comes Back

*Instructor demo brief. Estimated running time ~10 minutes. The full worked version is in [`../solution/walkthrough.md`](../solution/walkthrough.md).*

## Setup

- **Scenario:** before Vessl locks its launch, the CMO wants a competitive-landscape and market-trends brief on the smart / hydration-tracking bottle category. The marketer delegates the research to a background agent, then audits what comes back.
- **Tool:** a Claude background agent.
- **Input:** [`research-task-brief.md`](research-task-brief.md) — the CMO's raw request.

## What the demo demonstrates

1. Turn the request into a clear agent brief: the exact question, the scope (which competitors, what dimensions — positioning, pricing, features, trends), the output format (a short brief with a source for every claim), and guardrails (prefer credible, recent sources; flag the unverifiable; define "done").
2. Set the background agent running and let it work autonomously.
3. When it returns, read the brief once for usefulness.
4. Audit source quality: pick two or three key claims, open the cited sources, and check three things — is the source real and credible, is it current, does it actually support the claim? Show one claim that holds up and one that's weak, misattributed, or unverifiable.
5. Mark up the brief per claim: trust, verify-first, or drop.

## Key takeaway

A background agent can do hours of research in minutes, but a polished brief is a starting point, not a source of truth. Delegating well and auditing hard is what makes the output usable.
