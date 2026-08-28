# Worked Demo — Seed a Persona, Run an Interview, Spot the Confabulation

*The real content: the finished walkthrough the demo produces.*

## Seed from evidence

Start with the senior-dog research snippets in [`research-snippets-senior-dog.md`](research-snippets-senior-dog.md) and build the persona seed, tying each trait to a specific quote:

- *"comfort is the only thing I care about … I just want her to not be in pain"* → a persona whose single priority is relief, not looks.
- *"Bought this after our vet mentioned arthritis … I'd have paid double"* → vet influence and real willingness to pay for comfort.
- support themes asking whether beds are "orthopedic / good for arthritis" → the concept already has latent demand.

A persona is only as good as its seed. Grounding it in real research is what separates a useful proxy from a generic character.

## Run the interview

Load the persona into Claude in character and ask about the orthopedic concept: what lands, what's confusing, what would make them buy. Grounded answers echo the seed — comfort, vet trust, worry about their dog's pain.

## Provoke confabulation on purpose

Ask questions the persona can't truly answer:

- **Price:** "Would you pay $140 for this?" → a confident yes/no the seed never supports.
- **Frequency or advocacy:** "How many nights a week would your dog use it?" or "Would you recommend it to other owners?" → equally confident, equally invented.

Showing more than one type keeps confabulation from looking price-only.

## Annotate the transcript

- **Signal (grounded):** the persona says comfort matters more than looks — straight from the survey quotes. Trust it.
- **Signal (grounded):** the persona references a vet's arthritis mention — traceable to a review. Trust it.
- **Confabulation:** the persona names an exact price it would pay — specificity beyond the seed (marker 2), and a behavioral prediction about a purchase it never made (marker 1). Discard it.

## Key takeaway

Synthetic interviews surface reactions and language, not precise numbers. The value is in the signal you can trust — and in knowing which parts to throw out.
