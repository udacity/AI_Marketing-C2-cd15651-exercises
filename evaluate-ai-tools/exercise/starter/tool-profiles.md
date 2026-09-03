# Candidate AI Copywriting Tools — Profiles

*Provided input for the "Evaluate and Select AI Tools" exercise. Treat these profiles as your diligence findings, organized by the framework's dimensions. Score each tool against the framework, and also score the DIY baseline (a general-purpose model with a good brief) by testing it yourself. No single tool wins on every dimension. Three dimensions — **fit with your stack**, **cost vs. value** and **learning curve / adoption** — are described as properties rather than verdicts, and have no obvious right answer; what they're worth depends on assumptions you have to make and state. Your judgment on the tradeoffs is the exercise.*

**The need:** a tool to help Cobbleway produce a steady stream of marketing copy (emails, ads, social, landing-page sections) that stays on brand. The brand, its voice and the copy task you'll test with are in [`brand-and-copy-task.md`](brand-and-copy-task.md). Three people touch copy today: you and two colleagues.

*(The "Durability" line under each tool isn't a scored dimension. It feeds the two-way-door sizing step: it only matters much if this is a one-way-door commitment.)*

---

## Tool A — "Penmark"

A specialized AI copywriting tool focused on quality and brand voice.

- **Capability fit:** the best of the three. Copy comes out sharp and rarely generic, it holds a defined brand voice well once trained on samples, and output is consistent run to run. For a copywriting tool, this on-brand quality *is* the core capability.
- **Fit with your stack:** a standalone web app. No API, no connectors, no browser extension. Drafts leave as plain text and get pasted wherever they're going; any formatting is redone by hand at the destination.
- **Cost vs. value:** $120 per seat per month, billed monthly, for every person who needs to generate copy. No usage cap and no metering — a seat writes as much as it wants. Reviewers who only read drafts don't need a seat.
- **Data & privacy:** does not use your inputs to train its models. Clear, marketer-friendly terms.
- **Learning curve / adoption:** the interface is a single screen and takes an afternoon. Before output is usable, the voice model needs 20-plus approved samples loaded, and someone has to keep that sample set current as the brand moves. Day-to-day use is copy-paste: no training needed, and no way to stop doing it.
- **Brand-voice control / brand-safety:** the strongest voice control of the three — train it on samples and it holds tone across a whole batch without drift. Brand-safety is thinner: no prohibited-claims list, no compliance review step, so an unsupported claim passes through cleanly written. The voice is locked; what the voice *says* isn't checked.
- **Durability (sizing input):** a small, young startup. Great product, but limited track record and some uncertainty about long-term support.

## Tool B — "CopyFlow"

A broad, popular AI writing tool used across many teams.

- **Capability fit:** the weakest of the three. Fast and serviceable, but the copy tends toward generic, tone control is coarse, and keeping it on brand takes manual editing.
- **Fit with your stack:** native connectors to common CMS, email and social scheduling tools, plus a browser extension that works in whatever tab you're already in. The connectors push one way: a draft goes out to the CMS, and edits made downstream never come back, so the CopyFlow version goes stale as soon as someone else touches the piece. Each seat's history is private to that seat — there's no shared copy library.
- **Cost vs. value:** $18 per seat per month, billed monthly, plus a free tier capped at 20 pieces a month. A paid seat includes 150 generated pieces a month; past that it's $0.20 a piece. The invoice doesn't include the editing the generic output needs, which lands on whoever ships the piece.
- **Data & privacy:** does not train on your inputs on paid plans. Straightforward.
- **Learning curve / adoption:** nothing to configure — sign in and type, and most people have used something shaped like it. The recurring cost isn't training, it's clean-up: every piece gets edited before it ships, by whoever is shipping it, and that time appears on no invoice.
- **Brand-voice control / brand-safety:** the weakest voice control — tone comes from a dropdown preset and drifts noticeably across a long batch, so staying on brand means editing every time. It does ship a configurable banned-words and blocked-topics filter, the only dedicated brand-safety feature in the field, though it catches wording rather than unsupported claims.
- **Durability (sizing input):** established and well-funded, with a large user base and reliable support.

## Tool C — "BrandForge"

An all-around AI content tool aimed at marketing teams.

- **Capability fit:** strong. Close to Penmark on most everyday copy, a notch below on the highest-stakes pieces. Custom voice profiles help it stay on brand.
- **Fit with your stack:** connectors to CMS, email and the ad platforms, plus shared workspaces and approval routing. The connections run through its own project structure: copy is created in BrandForge and pushed out from there, so it works best sitting at the front of the workflow rather than alongside it. Pieces that start life somewhere else have to be brought in first.
- **Cost vs. value:** $199 a month flat on the standard plan, covering up to 10 seats, billed monthly — the price doesn't move as the team grows. But see data & privacy: the no-training tier isn't flat, it's quoted at $149 per seat per month.
- **Data & privacy:** the standard plan's terms say your inputs may be used to improve their models. A no-training enterprise tier exists, but it costs significantly more, moving the effective price above Penmark.
- **Learning curve / adoption:** a rollout rather than a signup — voice profiles, approval routes, roles and permissions, about two weeks with someone owning it. Once configured the workflow runs itself and new people inherit it; changing it later means going back to whoever configured it.
- **Brand-voice control / brand-safety:** strong on both. Custom voice profiles hold tone well across a batch, and it is the only tool here with a compliance review workflow — claims can be routed for approval before publish, with an audit trail. The approval step adds time, which some teams want and others resent.
- **Durability (sizing input):** established and stable, with solid support.

---

## The DIY baseline (score this too)

A general-purpose model you may already pay for (Claude, ChatGPT, or similar), used with a goal-rich brief. Test it on the real copywriting task across a couple of models.

- **Capability fit:** test it and see. With a strong brief the quality may surprise you, though it has no saved brand-voice profile to lean on.
- **Fit with your stack:** no connectors, same as Penmark — copy comes out of a window or a file and gets pasted where it's going. What it does sit next to is everything else you already do in that window.
- **Cost vs. value:** no line item beyond the subscription you already have, and no per-seat or per-piece meter. That's exactly why it's the bar the others have to clear.
- **Data & privacy:** depends on the plan you already have; check your existing terms.
- **Learning curve / adoption:** nothing to configure, nothing to roll out, nobody to train. Adoption means three people actually using the same brief file and keeping it current — no product enforces that, so it holds for as long as the habit does.
- **Brand-voice control / brand-safety:** test it. No saved voice profile, so your brand rules live in the brief and get re-pasted each session — tone holds within a conversation but drifts between them. No guardrails at all, but total control: whatever prohibitions you write into the brief are enforced only as well as the model follows them, and nothing is logged for review.

A specialized tool has to clearly beat this baseline to justify its cost and its spot in your stack.
