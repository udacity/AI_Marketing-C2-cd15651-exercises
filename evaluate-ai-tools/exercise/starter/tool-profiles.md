# Candidate AI Copywriting Tools — Profiles

*Provided input for the "Evaluate and Select AI Tools" exercise. Treat these profiles as your diligence findings, organized by the framework's dimensions. Score each tool against the framework, and also score the DIY baseline (a general-purpose model with a good brief) by testing it yourself. No single tool wins on every dimension, and on purpose, two or three dimensions have no obvious right answer. Your judgment on the tradeoffs is the exercise.*

**The need:** a tool to help produce a steady stream of marketing copy (emails, ads, social, landing-page sections) that stays on brand.

*(The "Durability" line under each tool isn't a scored dimension. It feeds the two-way-door sizing step: it only matters much if this is a one-way-door commitment.)*

---

## Tool A — "Penmark"

A specialized AI copywriting tool focused on quality and brand voice.

- **Capability fit:** the best of the three. Copy comes out sharp and rarely generic, it holds a defined brand voice well once trained on samples, and output is consistent run to run. For a copywriting tool, this on-brand quality *is* the core capability.
- **Fit with your stack:** weak. It's a standalone web app with no integrations. Everything is copy-paste in and out; no CMS, ad platform, or workflow connections.
- **Cost vs. value:** the most expensive option, at a premium per-seat monthly rate. You're paying up for output quality and giving up integration.
- **Data & privacy:** does not use your inputs to train its models. Clear, marketer-friendly terms.
- **Learning curve / adoption:** simple to learn, but the manual copy-paste workflow adds friction at scale.
- **Brand-voice control / brand-safety:** the strongest voice control of the three — train it on samples and it holds tone across a whole batch without drift. Brand-safety is thinner: no prohibited-claims list, no compliance review step, so an unsupported claim passes through cleanly written. The voice is locked; what the voice *says* isn't checked.
- **Durability (sizing input):** a small, young startup. Great product, but limited track record and some uncertainty about long-term support.

## Tool B — "CopyFlow"

A broad, popular AI writing tool used across many teams.

- **Capability fit:** the weakest of the three. Fast and serviceable, but the copy tends toward generic, tone control is coarse, and keeping it on brand takes manual editing.
- **Fit with your stack:** good. Native connections to common CMS, email, and social scheduling tools, plus a browser extension.
- **Cost vs. value:** the cheapest, with a low monthly rate and a generous free tier. Cheap, but the value depends on how much editing the generic output needs.
- **Data & privacy:** does not train on your inputs on paid plans. Straightforward.
- **Learning curve / adoption:** easy to adopt and already familiar to many teams.
- **Brand-voice control / brand-safety:** the weakest voice control — tone comes from a dropdown preset and drifts noticeably across a long batch, so staying on brand means editing every time. It does ship a configurable banned-words and blocked-topics filter, the only dedicated brand-safety feature in the field, though it catches wording rather than unsupported claims.
- **Durability (sizing input):** established and well-funded, with a large user base and reliable support.

## Tool C — "BrandForge"

An all-around AI content tool aimed at marketing teams.

- **Capability fit:** strong. Close to Penmark on most everyday copy, a notch below on the highest-stakes pieces. Custom voice profiles help it stay on brand.
- **Fit with your stack:** very good. Connects to most of the marketing stack and supports team workflows and approvals.
- **Cost vs. value:** mid-range on the standard plan, between the other two. But see data & privacy: the fix for the training issue raises the price above Penmark.
- **Data & privacy:** the standard plan's terms say your inputs may be used to improve their models. A no-training enterprise tier exists, but it costs significantly more, moving the effective price above Penmark.
- **Learning curve / adoption:** moderate. More setup than CopyFlow, but the team workflows help once it's in place.
- **Brand-voice control / brand-safety:** strong on both. Custom voice profiles hold tone well across a batch, and it is the only tool here with a compliance review workflow — claims can be routed for approval before publish, with an audit trail. The approval step adds time, which some teams want and others resent.
- **Durability (sizing input):** established and stable, with solid support.

---

## The DIY baseline (score this too)

A general-purpose model you may already pay for (Claude, ChatGPT, or similar), used with a goal-rich brief. Test it on the real copywriting task across a couple of models.

- **Capability fit:** test it and see. With a strong brief the quality may surprise you, though it has no saved brand-voice profile to lean on.
- **Fit with your stack:** none dedicated, similar to Penmark.
- **Cost vs. value:** little beyond what you already spend, which is exactly why it's the bar to beat.
- **Data & privacy:** depends on the plan you already have; check your existing terms.
- **Learning curve / adoption:** already in hand, no new tool to roll out.
- **Brand-voice control / brand-safety:** test it. No saved voice profile, so your brand rules live in the brief and get re-pasted each session — tone holds within a conversation but drifts between them. No guardrails at all, but total control: whatever prohibitions you write into the brief are enforced only as well as the model follows them, and nothing is logged for review.

A specialized tool has to clearly beat this baseline to justify its cost and its spot in your stack.
