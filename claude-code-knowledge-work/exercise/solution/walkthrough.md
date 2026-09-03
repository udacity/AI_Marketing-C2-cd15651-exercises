# Solution — Run the Session, Produce Three Connected Deliverables

*Worked solution — one strong example. Student deliverables will differ in wording; what matters is that all three are on-brand, visibly connected, built in one persistent workspace so context isn't re-pasted, and then reconciled against each other in a fresh session from the files on disk.*

**Setup:** a Claude Code project folder holding `brand-voice-guide.md` and `campaign-context-sheet.md`, with a short `CLAUDE.md` telling Claude Code to treat both as the campaign's source of truth.

---

## Deliverable 1 — Messaging brief (`messaging-brief.md`)

**Positioning:** Hydration, handled.
**Key messages:**
1. Your water bottle now keeps score, so you don't have to.
2. Automatic tracking — no logging, no guesswork.
3. Gentle nudges at the right moments, working quietly in a busy day.
4. Feel your best, without the effort.
**Tone:** encouraging, clear, a little witty; feeling first, tech second.
**Audience:** active, health-aware people 25–45 who already track steps/sleep and want one less thing to manage.

### Refinement step — how the brief got on-brand

The first pass was accurate but flat: a feature list, exactly what the voice guide warns against. One follow-up prompt, with the guide and campaign sheet already in the folder:

> These key messages read like a spec sheet. Rewrite them in the brand voice — lead with the feeling, use the campaign's hook, and cut anything that sounds like a feature list.

**First pass:** (1) real-time hydration tracking via in-bottle sensors; (2) the app shows your progress against your daily goal; (3) smart reminders when you fall behind; (4) better hydration supports better health.

**After:** the four key messages above. Claude pulled "keeps score, so you don't have to" straight from the campaign sheet's stated hook and the voice guide's message starters, because both were already in the workspace. The brief was edited in place — the draft never had to be pasted back in.

## Deliverable 2 — Launch email copy (`launch-email.md`)

Written after the brief was refined, so it inherits the sharpened key messages without being handed them again:

> **Subject:** Your water bottle just got a lot smarter
>
> Staying hydrated shouldn't take willpower or math. Meet Vessl — the smart water bottle that keeps score so you don't have to. It tracks every sip and gently nudges you when you're falling behind, so hitting your goal just… happens.
>
> No logging. No guessing. Just a quiet tap on the shoulder when you need it, and the good feeling of being on track by the end of the day.
>
> **This summer only:** early buyers get free shipping + 3 months of premium in the app.
>
> *Hydration, handled.* → [Get Vessl]

Carries key messages 1, 2, and 3 from the brief, in the brand voice, no fear/guilt framing.

## Deliverable 3 — Creator profile (`creator-profile.md`)

**Who we want:** an active, health-aware creator (fitness, wellness, or "day in the life" productivity) whose real routine already includes movement and hydration — someone who can show Vessl fitting naturally into their day, not read an ad.
**Audience:** 25–45, health-curious, skeptical of hype.
**Content style:** candid, daylight, real-moment; product in-frame, not staged.
**Values fit:** helpful over preachy; celebrates small wins; calm and capable — matches Vessl's "supportive friend" personality.
**Why they fit:** their audience *is* our audience, and authentic daily use is the campaign's whole creator-led thesis.

---

## Refinement step

With all three files in the workspace, one follow-up prompt refines without re-pasting context:

> Tighten the email's opening paragraph to two sentences. It should open on the feeling, not the feature — no mention of tracking in the first line.

Claude has the email already open in the workspace and returns the revision in context — no copy-pasting the draft back in.

**Watch what this costs.** The revision opens on the feeling as asked, but the paragraph it replaced was where "keeps score so you don't have to" and "tracks every sip" lived — the campaign's stated hook and the tracking claim behind it. The email is now shorter, better, and quietly no longer says what the product does. Nothing in the session flags it, because the session is looking at one file and it was asked to cut, not to keep.

## Fresh session — reconcile the three files (`consistency-check.md`)

Close the session. Reopen the same folder and ask for the check in one prompt, without describing what's in any of the files:

> Read messaging-brief.md, launch-email.md and creator-profile.md in this folder. Check them against each other and against brand-voice-guide.md: does the email carry the brief's key messages, does the creator profile's audience match the brief's, and does every piece follow the voice guide? Write what you find to consistency-check.md, naming the file and the specific disagreement.

Claude Code reads all four files off disk and returns two findings plus a clean voice check — see [`example-output.md`](example-output.md) for the note it wrote. The headline finding is the cost of the refinement above: the tightened email lost key message 1 outright and kept only half of message 2, so it now promises "no logging, no guessing" without ever saying that Vessl tracks. The subtler one is a one-word audience slide in the creator profile — the brief's "health-aware, already tracking" became "health-curious," a softer, browsing audience.

**Why this needs a fresh session, not a scroll-back.** Two things are being tested at once. The files have to still be on disk after the session that made them is gone — that's the persistent workspace. And the reconciliation has to be a *read*, not a recollection: a session that drafted the email remembers writing "tracks every sip" and will happily tell you it's still there. A session that has never seen the email only knows what the file says. That is the whole reason the check catches the drift.

Both findings are fixable in the same fresh session, because the files are right there: restore the "keeps score" hook to the email as a third sentence that keeps the feeling-first opening, and align the creator profile's audience line to the brief's wording.

## Where persistent context helped (the one-line note)

> Writing the launch email, I didn't re-paste the brand voice or the brief — Claude Code already had both from the project folder, so the email inherited the key messages and tone automatically. A week later a session that had never seen any of it caught a claim the refinement had dropped, just by reading the files.

## Common mistakes

- Re-pasting the brand guide into every prompt instead of loading it once into the workspace.
- Three disconnected pieces that don't build on each other (email ignores the brief's key messages).
- Drifting off-brand — clinical/spec language, or fear-based "you're dehydrated" framing.
- Running the consistency check in the same session that wrote the deliverables. It will confirm from memory what it meant to write, not from the file what it actually wrote, and the drift survives.
- Pasting the three deliverables into the fresh session's prompt. That's a chat window with attachments — the point is that the folder already holds them.
- A consistency-check note that says "all consistent" without naming what was compared. If it can't show the pairings it checked, it hasn't checked anything.
