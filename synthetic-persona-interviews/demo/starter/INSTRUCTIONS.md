# Demo — Seed a Persona, Run an Interview, Spot the Confabulation

*Instructor demo brief. Estimated running time ~12 minutes. The full worked version is in [`../solution/walkthrough.md`](../solution/walkthrough.md).*

## Setup

- **Scenario:** Barkwell (a dog bed company) is considering an orthopedic bed line for aging dogs, and wants to pre-test the concept with a synthetic persona.
- **Tools:** Claude Code; the [`persona-seed-template.md`](persona-seed-template.md).
- **Input:** [`research-snippets-senior-dog.md`](research-snippets-senior-dog.md) — reviews, survey quotes, and support themes for an owner of a senior dog.

## What the demo demonstrates

1. Show the raw research snippets. Build the persona seed from them, tying each trait to a piece of evidence.
2. Load the persona into Claude with interview framing ("you are this person, answer in their voice").
3. Ask about the orthopedic bed concept: what lands, what's confusing, what would make them buy.
4. Deliberately ask questions the persona *can't* truly answer — start with price ("would you pay $140?"), then a second type such as frequency or advocacy. Show how each produces a confident but fabricated answer.
5. Annotate the transcript: mark two moments of real signal (grounded in the seed) and one moment of confabulation (invented beyond the evidence), naming which marker gave it away.

## The two confabulation markers

- A behavioral prediction about something the persona has never actually experienced.
- Specificity beyond what the seed data supports (a precise number or vivid detail the research never gave it).

## Key takeaway

Synthetic interviews are for surfacing reactions and language, not for extracting precise numbers. The marketer's job is to seed well and read skeptically.
