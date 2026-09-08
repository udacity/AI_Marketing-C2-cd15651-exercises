# Sample Output — Four Connected Deliverables

*Actual Claude output — three campaign files produced in one Claude Code project workspace, each drawing on the brand + campaign files (and the earlier deliverables) without re-pasting, then a fourth file reconciling them in a fresh session from the saved files. One run; outputs vary.*

*The filenames below are this run's own. The exercise asks for one file per deliverable and doesn't prescribe names — any clear name works, as long as the consistency check names the files it actually read.*

## 1. `messaging-brief.md`
- **Positioning:** Hydration, handled.
- **Key messages:** (1) your bottle keeps score, so you don't have to; (2) automatic tracking, no logging; (3) gentle nudges in a busy day; (4) feel your best, without the effort.
- **Tone:** encouraging, clear, a little witty — feeling first, tech second.
- **Audience:** active, health-aware, 25–45; already track steps/sleep; skeptical of hype.

## 2. `launch-email.md` — as first drafted
> **Subject:** Your water bottle just got a lot smarter
>
> Staying hydrated shouldn't take willpower or math. Meet Vessl — the smart water bottle that keeps score so you don't have to. It tracks every sip and gently nudges you when you're falling behind, so hitting your goal just… happens.
>
> No logging. No guessing. Just a quiet tap on the shoulder when you need it, and the good feeling of being on track by the end of the day.
>
> **This summer only:** early buyers get free shipping and three months of premium in the app.
>
> *Hydration, handled.* → **[Get Vessl]**

*(As first drafted, this carries key messages 1, 2, and 3, in the brand voice, with no fear/guilt framing. The refinement below rewrites the opening and costs it two of those — the final file is at the end of that section, and §4 is the audit that catches it.)*

## 3. `creator-profile.md`
> **Who Vessl should partner with:** an active, health-aware creator — fitness, wellness, or "day in the life" — whose real routine already includes movement and hydration. **Audience:** 25–45, health-curious, skeptical of hype. **Content style:** candid, daylight, real-moment; product in-frame, not staged. **Values fit:** helpful over preachy, celebrates small wins — matches Vessl's "supportive friend" voice. **Why:** their audience *is* our audience, and authentic daily use is the campaign's whole creator-led thesis.

## Refinement (`launch-email.md` opening, revised)

Prompt: *"Tighten the email's opening paragraph to two sentences. Open on the feeling — no feature mention in the first line."*

**Before:**
> Staying hydrated shouldn't take willpower or math. Meet Vessl — the smart water bottle that keeps score so you don't have to. It tracks every sip and gently nudges you when you're falling behind, so hitting your goal just… happens.

**After:**
> You're already doing the hard part — moving, sleeping, showing up. Vessl handles the one thing that quietly makes all of it work better.

*(One prompt, no re-pasting. Claude held the brand voice and the brief's "feeling first" instruction from the project files.)*

**Final `launch-email.md`, as it now sits on disk:**

> **Subject:** Your water bottle just got a lot smarter
>
> You're already doing the hard part — moving, sleeping, showing up. Vessl handles the one thing that quietly makes all of it work better.
>
> No logging. No guessing. Just a quiet tap on the shoulder when you need it, and the good feeling of being on track by the end of the day.
>
> **This summer only:** early buyers get free shipping and three months of premium in the app.
>
> *Hydration, handled.* → **[Get Vessl]**

**This assembled version is what §4 audits, and it no longer carries all three key messages.** Message 1 — "keeps score, so you don't have to" — left with the paragraph that got tightened, and the tracking half of message 2 went with it. Nothing in this session says so: the file reads better and scores worse against the brief, and only a reader coming to it cold would catch that. Don't quietly repair it before you run the check — the consistency check is the deliverable, and it needs something real to find.

## 4. `consistency-check.md` — written in a fresh session

Session closed, folder reopened. One prompt, nothing pasted in:

*"Read messaging-brief.md, launch-email.md and creator-profile.md in this folder. Check them against each other and against brand-voice-guide.md: does the email carry the brief's key messages, does the creator profile's audience match the brief's, and does every piece follow the voice guide? Write what you find to consistency-check.md, naming the file and the specific disagreement."*

**Claude Code's output → `consistency-check.md`:**

> # Vessl Summer Launch — Consistency Check
>
> **Read from disk:** `brand-voice-guide.md`, `campaign-context-sheet.md`, `messaging-brief.md`, `launch-email.md`, `creator-profile.md`. Three pairings checked: brief → email, brief → creator profile, voice guide → all three.
>
> ## Drift 1 — `launch-email.md` lost the brief's key message 1, and half of key message 2
>
> Message by message, against the brief:
>
> | Brief key message | In the email? |
> |---|---|
> | 1 — keeps score, so you don't have to | **No.** Nowhere in the body. |
> | 2 — automatic tracking, no logging | **Half.** "No logging. No guessing." survives; the tracking claim does not. |
> | 3 — gentle nudges in a busy day | Yes — "a quiet tap on the shoulder when you need it." |
> | 4 — feel your best, without the effort | Yes — the new opening, and "the good feeling of being on track." |
>
> The email now promises an absence without ever naming the mechanism: it says there's no logging and no guessing, but never says that Vessl tracks. "Keeps score, so you don't have to" — the campaign's stated hook, per `campaign-context-sheet.md` — is gone from the body entirely. The only surviving reference to what the product does is the subject line, "your water bottle just got a lot smarter," which a reader who opens the email has already scrolled past.
>
> **Likely cause:** the revision that tightened the opening replaced the paragraph holding both the "keeps score" line and "it tracks every sip." The instruction was "no feature mention in the first line"; the result removed the product from the whole first paragraph.
>
> **Fix:** keep the new opening — it is better, and it is on-brand. Restore the hook as the third sentence, after the feeling and before the offer. The brief's message 1 wording works as-is.
>
> ## Drift 2 — `creator-profile.md` softens the brief's audience
>
> The brief's audience is "active, health-aware, 25–45; already track steps/sleep." The creator profile's audience line reads "25–45, health-curious, skeptical of hype."
>
> "Health-curious" is a browsing audience; "health-aware, already tracking" is a committed one, and it's the audience the whole positioning assumes. The profile's own opening sentence says "health-aware," so the two halves of that file also disagree with each other. Small, but it's the line a partnerships team would brief an agency from.
>
> **Fix:** change to "health-aware, already tracking steps or sleep" to match the brief.
>
> ## Voice guide — clear across all three
>
> - No fear or guilt framing about dehydration in any file.
> - No clinical or spec-sheet language; nothing like "fluid-intake analytics."
> - No wellness mysticism.
> - Second person throughout, short sentences, feeling before tech.
> - **One judgment call, not a violation:** the subject line's "got a lot smarter" leans further into product hype than the guide's "calm and capable" preference. It stops short of the banned words ("revolutionary," "game-changing"). Flagging, not failing.
>
> ## Consistent — confirmed, not assumed
>
> - Positioning line "Hydration, handled." is identical in the brief, the email sign-off, and the profile's rationale.
> - The launch offer in the email (free shipping + three months of premium) matches `campaign-context-sheet.md` exactly.
> - The creator profile's content style (candid, daylight, real-moment) matches the voice guide's look-and-feel section.
>
> **Summary:** two drifts, both introduced downstream of the brief, both fixable in this session. One is load-bearing — the email sells a feeling with no product behind it.
>
> **Where persistent context saved me:** I never re-pasted the brand voice or the brief to write the launch email, and I didn't have to re-explain them in the fresh session either — it read all five files off disk and caught the "keeps score" hook my own refinement had deleted.

*That last line is the required one-line persistent-context note, and it lives inside the consistency-check file as its final line — not in a fifth file of its own.*
