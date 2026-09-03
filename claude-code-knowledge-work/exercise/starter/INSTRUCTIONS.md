# Run the Session, Produce Four Connected Deliverables

Vessl is running a creator-led summer launch, and you're producing the campaign's core pieces. Set up a Claude Code project workspace and produce four connected deliverables: three campaign pieces, each building on the last, all in the Vessl brand voice — then, before the campaign goes to review, a fourth that checks whether those three actually agree with each other.

Work in Claude Code, in a project folder that holds the campaign's files. Put these in the folder as your persistent context:

- [`brand-voice-guide.md`](brand-voice-guide.md) — the brand's source of truth for tone, language, and look.
- [`campaign-context-sheet.md`](campaign-context-sheet.md) — the launch campaign details.

## What to produce

Three campaign pieces, each saved as a file in the project folder:

- **Messaging brief** — positioning, three to four key messages, tone, and target audience. Refine it over a few turns until it's on-brand.
- **Launch email copy** — drawing on the messaging brief and brand voice already in the folder, without re-pasting them. It should clearly carry the brief's key messages.
- **Creator profile** — the type of creator Vessl should engage for sponsorships: their audience, content style, values, and why they fit the brand and campaign, grounded in the brief's audience and positioning.

Then a fourth file, produced in a **fresh session**:

- **Consistency-check note** — close your session, then reopen the same project folder in a new one and have Claude Code read the three saved deliverables back off disk and reconcile them against each other and against the brand-voice guide. Does the email carry the brief's key messages, or has it dropped or invented one? Does the creator profile's audience match the brief's? Does every piece obey the voice guide? Save a short note that names each piece of drift you find — which file, and what disagrees with what — or states that there is none.

Plus a one-line note on where the workspace's persistent context saved you from re-explaining something — add it as the last line of the consistency-check file.

## Requirements

- Keep the brand-voice guide and campaign-context sheet in the project folder (point Claude Code at them, e.g. via `CLAUDE.md`), so the deliverables ground in Vessl's actual voice, not a generic guess.
- The three pieces must be connected: the messaging brief should shape the email, and both should shape the creator profile. Build each in the same workspace so it draws on the files already there, rather than starting cold.
- Stay in the brand voice throughout — encouraging, clear, a little witty, never preachy or clinical. Lead with how people feel, then the tech. No fear or guilt framing about dehydration.
- Save each deliverable as its own file and refine it in place.
- Run the consistency check in a genuinely fresh session, after closing the first. Don't summarize the deliverables for Claude Code and don't paste them back in — it should reconcile them by reading the saved files. If you have to re-paste anything, your working context was never on disk.
- Report what you actually find. "No drift" is a real result, but only if the note shows what was compared against what.

## Done when

You have three files that share one brand voice and visibly build on each other, plus a consistency-check note — produced in a fresh session, from the saved files rather than anything you re-pasted — that names the drift between them or confirms there is none. And your one-line note points at a specific moment the workspace's persistent context saved you from re-explaining something, not a general claim that it helped.
