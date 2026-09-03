# Worked Demo — Score One Tool Against the Framework

*The real content: the finished walkthrough the demo produces.*

## Why a framework at all

Most tool decisions are made on demo dazzle, not fit. The framework forces the boring questions that actually predict success. Its dimensions:

- **Capability fit** — does it do the specific job well and dependably, on your real task?
- **Fit with your stack** — does it connect to what you already run, or is it copy-paste?
- **Cost vs. value** — is the price justified against a baseline, not against zero?
- **Data & privacy** — where does your data go; is it used to train their models?
- **Learning curve / adoption** — can you and your team actually roll it out?
- **Brand-voice control / brand-safety** — can you keep output on-brand and compliant? This is the marketing-specific dimension generic checklists miss.

## The tool on the table

**Draftwell**, an AI copywriting tool built specifically for email. It sits inside your sending platform, learns a voice from your past sends, and drafts subject lines, promo copy and newsletter bodies against it.

The real task, not the vendor's: our recurring email programme. One newsletter a week, a six-email welcome sequence, and two promo sends a month — **about 20 pieces of email copy a month**, written today by one person against a one-page voice guide (tone rules plus an avoid list). That guide is all the brand context the scoring needs; you don't need a brand book to judge whether output sounds like you.

## Scoring one tool (worked)

Go dimension by dimension and narrate the reasoning out loud:

- **Capability fit:** run the real work, not the vendor's sample. We put the last two months of actual sends through the trial — 41 pieces. Subject lines and the short promo sends came back shippable. The weekly newsletter body, about 400 words, came back competent and structurally flat; roughly half got reordered by hand before sending. Strong on short form, mediocre on the long piece — and the long piece is where the programme's clicks come from.
- **Brand-voice control / brand-safety:** zero avoid-list violations across all 41, and no drift at all — the tone at piece 41 was the tone at piece 1. Then read the batch instead of the sample: every email opens on the same rhetorical move and closes on the same cadence. Nothing is off-brand. The brand just starts sounding automated. There's also no claims check — the tool asks whether a sentence is on tone, never whether it's true.
- **Fit with your stack:** it runs inside the email platform we already send from. Drafts arrive as real drafts in the ESP, and edits made there flow back, so there's no second copy going stale in a second tool. It only does email — which costs us nothing, because our job is only email. The identical limitation would be a 2 if we were also buying it for landing pages. Fit is scored against your job, not against the feature list.
- **Cost vs. value:** unlimited seats, priced per thousand subscribers. The meter runs on the list, not the team — which is to say it runs on the number we're trying to grow.
- **Data & privacy:** where does the data go, and how much of it? Read the terms before you score this, not after — and count the footprint, not just the clauses.
- **Learning curve / adoption:** this is a migration, not a signup. Before the voice model is worth anything it wants twelve months of past sends imported and tagged, and the ESP connector is configured by the vendor's team on the vendor's calendar. Three to four weeks to a first usable draft, all of it landing on the one person who is also still writing the copy that month.

Note where that second observation *lands*. Sameness is not a capability failure — each of the 41 drafts is fine on its own, and a tool that never drifts is doing exactly what it promised. It's a brand-voice finding, because voice is a property of the batch, not of the draft. Deciding which dimension owns a finding is half the work — and it's why you read the batch instead of the sample.

## Stress-test a score

Don't just total the scores — argue with them. Ask Claude: *"I gave cost vs. value a 4 because it's under $100 a month at our list size. Am I being too generous?"*

The pushback lands twice. First: you scored this month's invoice for a meter that runs on list growth, and the plan for this year roughly triples the list. Score the price at the volume you're committing to, not today's. Second: the framework says price it against a baseline, not against zero — and we haven't tested the baseline, so "cheap" is currently being measured against nothing.

**The 4 became a 3.** Scores are supposed to move when you argue with them; a scorecard nobody argues with is just a form. And the second half of that answer is the reason the next beat exists.

## Build-vs-buy (the beat that matters most)

Before you buy anything, try to do the job with what you already have. So: the same month of work — the same 20 pieces, the same voice guide, this time written up as a brief file and put in front of a general model we already pay for. Two models, so we're not judging one model's good day.

On the copy, the baseline wins. Given the voice guide as a brief, the newsletter bodies came back better structured than Draftwell's — a flat 400-word middle is exactly what a strong general model fixes once it's told what the piece is for. On the short pieces it's a tie.

Where the baseline loses is everything around the copy. It remembers nothing between sessions, so the brief gets re-pasted every time and it's a person, not the tool, holding the voice across twenty pieces. And nothing lands in the send tool: every piece is a copy-paste, and the draft in the chat and the draft in the ESP diverge the moment anyone edits one.

So the verdict is a split, and naming the split is the useful part: **the baseline wins on the copy and loses on the plumbing.** That turns a vague buying question into an answerable one — are we paying for writing, or for a sync? Because if it's the sync, a copywriting tool is an expensive way to buy one. Sometimes the baseline clears the bar outright and you buy nothing at all; here it clears half of it. Either way, the near-free option you already own is the bar every paid tool has to clear, and you find out by running it, not by assuming.

## Size the decision

Match rigour to stakes — and check which way the door swings. Leaving is easy: the copy lives in the ESP as drafts we own, and cancelling costs a month's notice. *Entering* is not: three to four weeks of import, tagging and vendor-side setup that you don't get back if it doesn't work out. The expensive door is the one on the way in. That's an unusual shape, and it changes the remedy — you don't de-risk this with a longer contract review, you de-risk it by making the entry smaller. On durability: the vendor is two years old and the whole integration is built on one ESP's API, so its future is tied to a partnership as well as to its own funding — which matters here precisely because the setup cost is paid up front.

## The verdict

Total it, then state one call — **adopt, pilot, or pass** — and name the tradeoff you accepted.

**Pilot, one stream only:** the weekly newsletter, migrated with that archive and nothing else. Six issues, six weeks — days of setup instead of weeks. It's the piece the programme's clicks come from and the piece the tool scored worst on, so it's where the answer actually lives.

*Why not a pass:* we scored a cold tool. The vendor's claim is that the voice model earns its keep once it's fed, and the two scores dragging the total down — capability and brand-voice, both 3 — are the exact two that claim is about. That doesn't get settled by reading a pricing page. *Why not an adopt:* the only way to test the claim is to pay the expensive part of owning the tool, so we buy the smallest version of it that can still answer the question. **Kill criterion, written down before we start:** if by issue six the bodies still get reordered by hand, or the six read as one email written six times, we stop — because then we were only ever buying the sync, and there are cheaper syncs. **Tradeoff accepted:** a 2 on adoption, taken knowingly — we are spending the scarcest thing we have, the copywriter's month, to buy information.

The value isn't the number. It's the documented reasoning you can hand to a skeptical manager.

## Scaling to more options

One tool and a baseline fit in a table with the reasoning inside it. Four options don't — at that width the Reasoning column stops fitting on a page. So it moves rather than disappears: scores stay in the grid, the *why* becomes a short findings note below it (one bullet per option), and the memo carries the call. Same reasoning, relocated.

## Key takeaway

A structured evaluation converts an impulse into a recommendation. The scorecard is what lets you say no to a shiny tool and yes to the right one, with reasons — and the honest first question is always whether a good brief and the tools you already pay for would do the job.
