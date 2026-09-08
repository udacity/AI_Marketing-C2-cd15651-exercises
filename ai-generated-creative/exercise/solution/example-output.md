# Sample Output — One Concept, Three Formats

*Actual Claude output for the direction, self-contained prompts, and copy from the brand-voice guide + creative brief. One run; outputs vary.*

*What the images in this folder are, precisely: **HTML/CSS layout comps**, not AI-generated photography. A stylised vector bottle stands in for the photographic plate your image tool produces, because no image tool runs in this environment. They are here so you have a real reference for the half of the job a prompt can't do — type placement, negative space, palette discipline, and the tagline and CTA composited on top. **Your version should put a generated photo where the vector bottle is.** Nothing below claims an image tool produced these.*

**Concept — "Caught mid-day, mid-life — hydrated without trying."** A real person in an unstaged daytime moment, Vessl bottle naturally in frame.

## The three prompts (for your image tool)

**Self-contained image prompt (1:1 feed):**
> Editorial lifestyle photo, natural daylight, airy and fresh. A 30-something person mid-motion in a bright modern apartment doorway, canvas tote on shoulder, holding a matte smart water bottle with a subtle LED ring. Cool aqua / soft-blue palette, clean white surroundings, one warm coral accent (a scarf). Candid, shallow depth of field, condensation on the bottle. Open space top-left for a headline and tagline, clear space bottom-left for a CTA button. No logos, no text in image.

**Copy:** Headline — "It keeps score, so you don't have to." · Tagline — "Hydration, handled." · CTA — "See how it works"

**Self-contained image prompt (9:16 story):**
> Editorial lifestyle photo, vertical 9:16 crop, natural daylight, airy and fresh. A 30-something person mid-motion in a bright modern apartment doorway, canvas tote on shoulder, holding a matte smart water bottle with a subtle LED ring — subject in the lower third of the frame. Cool aqua / soft-blue palette, clean white surroundings, one warm coral accent (a scarf). Candid, shallow depth of field, condensation on the bottle. Generous open space across the top third for stacked text, clear space bottom-centre for a CTA button. No logos, no text in image.

**Self-contained image prompt (16:9 banner):**
> Editorial lifestyle photo, wide 16:9 crop, natural daylight, airy and fresh. A 30-something person mid-motion in a bright modern apartment doorway, canvas tote on shoulder, holding a matte smart water bottle with a subtle LED ring — subject pushed to the right third, bottle sharp and in focus. Cool aqua / soft-blue palette, clean white surroundings, one warm coral accent (a scarf). Candid, shallow depth of field, condensation on the bottle. Open space across the left half for a headline and tagline, clear space bottom-left for a CTA button. No logos, no text in image.

Each variant is a full standalone prompt, not a delta off the 1:1 — the image tool remembers nothing between runs. Concept, palette, and message hold constant; only the frame, subject position, and negative space move.

Paste each prompt into the AI image tool of your choice and generate it there — none of Claude Code's context travels with it, which is exactly why each prompt has to stand on its own.

**On "no text in image":** image tools render type unreliably, so the prompts ask for clean plates with the space reserved. The headline, the **"Hydration, handled."** tagline, and the **"See how it works"** CTA are composited afterwards, which keeps all three lines pixel-identical across all three frames.

## The composited layouts

| Frame | Layout comp | Render | Where the type sits |
|---|---|---|---|
| 1:1 feed | [`variant-1x1.html`](variant-1x1.html) | [`variant-1x1.png`](variant-1x1.png) | Headline and tagline top-left, CTA bottom-left, bottle right of centre |
| 9:16 story | [`variant-9x16.html`](variant-9x16.html) | [`variant-9x16.png`](variant-9x16.png) | Stacked and centred across the top third, CTA bottom-centre, subject lower third |
| 16:9 banner | [`variant-16x9.html`](variant-16x9.html) | [`variant-16x9.png`](variant-16x9.png) | Left half, CTA bottom-left, subject in the right third |
| 1:1 — **rejected first pass** | [`first-pass-1x1.html`](first-pass-1x1.html) | [`first-pass-1x1.png`](first-pass-1x1.png) | Everything stacked over a centred bottle |

One concept, three frames, same headline and tagline. Notice what stays fixed and what moves: the copy and palette never change, while the subject position and the reserved negative space are re-cut per frame. That is the difference between adapting a concept and restarting it three times.

## Iteration note — what was wrong and what changed

Open [`first-pass-1x1.png`](first-pass-1x1.png) next to [`variant-1x1.png`](variant-1x1.png). The first pass fails on brand, and the critique names four specific things rather than calling it "off":

1. **The warm accent became the whole palette.** The brand guide asks for a clean white base, cool aquas and soft blues, and *one* warm accent. The first pass is a full coral wash, which reads as hype — the exact register the guide rules out. **Fixed:** white and aqua base restored; coral kept only on the CTA, where it does a job.
2. **The subject was dead-centre, so nothing else had anywhere to go.** With the bottle in the middle, the headline had to sit on top of it and the CTA landed *across* it, obscuring the hero. **Fixed:** subject moved right of centre, freeing an uninterrupted column for type.
3. **The type was shouting.** Uppercase, extra-bold, drop-shadowed. The guide asks for encouraging, never boastful, and a friendly sans. **Fixed:** sentence case at a lighter weight, no shadow.
4. **Nothing could breathe.** 32px margins and a tagline crushed against the bottom edge, in a brand whose mood is "lots of open space." **Fixed:** 96px margins, and the tagline given air beneath the headline.

The change that mattered most was **moving the subject off-centre**. The palette and type problems were visible immediately, but the centred bottle was the one causing the others — it left no legible home for the headline or the CTA, so both ended up on top of the product. Reserve the negative space first, then set the type into it; that ordering is what the three prompts above are trying to buy you when they specify where the open space goes.
