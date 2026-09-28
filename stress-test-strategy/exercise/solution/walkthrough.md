# Solution: Run a Real Red Team on High-Stakes Copy

*Worked solution, one strong example. Outputs vary, what matters is a well-constructed red team (persona + goal + explicit attack + mitigations), a V2 that visibly fixes the surfaced risks, and a change memo that ties each edit back to a risk.*

## 1. Write V1 (and notice it doesn't push back)

Ask Claude to write the launch email, and give it the angle:

> "Write a launch email announcing Flowline AI... Lead with a bold, confident promise that Flowline AI basically runs your day for you, and drive hard to the upgrade."

It writes a polished, confident email built exactly around that promise, and it never flags that "runs your day for you" is a claim the feature can't keep. On its own, it runs with your premise. That's V1, and it's exactly why the review is your job.

## 2. Set the red team up deliberately

A good adversarial prompt has three moving parts. Weak prompts ("any feedback?") get you line edits; this gets you a real critique:

> "Act as a skeptical Product Marketing Manager who thinks this email is a mistake to send as written. Your goal is durable trust and paid retention, not click-through. Red-team the email you just wrote: call out each thing that isn't working and why it's a risk, be specific about second-order effects like trust, refunds, and unsubscribes, and give me a mitigation for each."

- **Persona:** skeptical PMM (a hostile lens, not a helpful assistant).
- **Goal:** durable trust and retention, not click-through (this is what makes it attack overpromising instead of optimizing for opens).
- **Explicit job:** red-team, name the risk and the second-order effect, propose a fix.

## 3. What a strong red team surfaces

For this email, the high-value critiques are all about what happens *after* the click:

- **Overpromise on an unproven feature.** "Runs your day for you" breaks the moment the first suggested plan is even slightly off, week-1 refunds, chargebacks, tickets that quote the email.
- **A bold claim with zero proof.** No beta stat, no hedge, reads as AI-hype bravado to a skeptical freemium list.
- **No off-ramp.** No trial or money-back, "trust us and pay" converts the people most likely to cancel in month one.
- **No failure framing.** Nothing says "you're in control, it suggests and you override," so every disagreement becomes a broken-promise moment.
- **Unsegmented blast.** Cold, unearned claim to dormant users, raises unsubscribe/spam-complaint risk and hurts future deliverability.
- **No humility, and a dark-pattern P.S.** ("upgrade sooner") that sophisticated users clock immediately.

Optional but sharp: judge the critique. A note like "this will permanently damage the brand" is overstated for one email, keep the substantive fix, discount the doom framing.

## 4. Turn it into V2

V2 has to visibly fix the risks, not just soften tone. A strong V2:

- Reframes the headline from "runs your day for you" to something honest about what it does (a daily starting plan built around what matters), removing the pass/fail promise.
- Makes user control an explicit, named feature (overriding a suggestion is normal, not a failure).
- Adds an upfront humility line about day-one imperfection, which does the job the missing beta data would have.
- Softens the CTA when there's no trial/refund to de-risk the ask (e.g., "See Flowline AI" and "judge for yourself" instead of a hard upgrade push).
- Repurposes the P.S. from manufactured urgency into a feedback invitation.

## 5. The change memo

A tight, skimmable list, each change tied to the risk it fixes:

> - Softened the headline claim, removes the all-or-nothing promise that breaks trust the moment one suggestion is off.
> - Made user control an explicit feature, reframes overriding a bad suggestion as expected behavior.
> - Added an upfront humility line, substitutes for beta data we can't cite; sets honest expectations.
> - Replaced the hard CTA with a softer ask, appropriate with no trial/refund to de-risk it.
> - Dropped the manufactured-urgency P.S., removes a dark pattern skeptics would notice.
> - Wrote the copy to hold up for the whole unsegmented list, lowers unsubscribe/spam risk.

## Common mistakes

- Skipping the persona and goal, "review this" gets you copy edits, not a red team.
- Collecting the critique but never producing a V2 that addresses it.
- Optimizing V2 for click-through when the stated goal was durable trust.
- No memo, so there's no evidence the review changed anything or why.
