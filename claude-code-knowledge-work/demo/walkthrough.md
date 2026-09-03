# Worked Demo — Set Up a Project Workspace, Build a Review-Response Kit

*The real content: the finished walkthrough the demo produces.*

Vessl's reviews are piling up across the store site, the app store, and a retailer listing. Support is answering them ad hoc, and it shows — some replies are warm, some read like a warranty notice. The job is a review-response kit that holds one voice, and that still holds it next week when the next batch lands.

## A project folder is a persistent workspace

Create a folder for Vessl's review responses and put [`brand-voice-guide.md`](brand-voice-guide.md) and [`customer-reviews-week-1.md`](customer-reviews-week-1.md) in it. Point Claude Code at them — a short `CLAUDE.md` saying "always work from these files; the voice guide governs every reply" is enough. Now every request in this folder works from that context; you never re-paste your brand guidelines again.

## Files become grounding

Ask Claude Code to build the response playbook. It reads the six reviews, sorts them into tiers, and writes the reply rules from the voice guide's own language — "encouraging, never nagging," "clear, never clinical," celebrate small wins, no fear or guilt. The don't-say list comes out of the guide's banned moves, not a generic support template.

## Save it, then refine in place

Write the playbook to `response-playbook.md` and refine it over a couple of turns. The obvious gap on first pass: the refund request in R-106 has no tier of its own, because a second failed unit isn't a complaint you can answer with warmth and a workaround. Add an escalation tier and a rule that support never improvises a refund in public. The file is the deliverable, edited in place rather than buried in a scroll of chat.

## The payoff compounds

Now ask for the replies themselves, saved to `replies-week-1.md`. Claude Code already has the reviews, the voice guide, and the playbook from the folder — no re-pasting — so it drafts six replies to the standard you just set. Then ask for one more thing that builds on all of it: `review-themes.md`, a digest of what's actually recurring across the batch and what belongs with the product team rather than support. Each new deliverable reuses the workspace's context and the files already on disk.

## It persists

Close the session. A week later the next batch of reviews arrives — drop [`customer-reviews-week-2.md`](customer-reviews-week-2.md) into the same folder and reopen it. Claude Code picks the folder up from `CLAUDE.md` and the files on disk, so a single prompt — "draft replies to the new reviews using the playbook" — gets replies that match last week's, and it flags that R-109's sensor drift is the tracking-reliability theme showing up again. Nothing was re-explained, because nothing was lost.

## Key takeaway

A Claude Code project folder turns a one-off answer into a workspace where recurring work can live — the standard you set once is still on disk, still governing the next batch, weeks later.
