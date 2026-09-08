# Solution — One Concept, Three Formats, On Brand

*Worked solution — one strong example. Concept and copy will vary; what matters is one clear concept, self-contained prompts that carry the brand without external context, three consistent formats, and evidence of an iteration loop.*

*On what's in this folder: the photographic plates come from an image tool that doesn't run in this environment, so the visual artifacts here are **HTML/CSS layout comps** with a stylised vector bottle standing in for the generated photo. They cover the compositing half of the job — where the type sits, how much space it gets, and how the palette is held across three frames. A learner's version should have a generated photo where the vector bottle is.*

## The concept

**"Caught mid-day, mid-life — hydrated without trying."** A real person in an unstaged daytime moment (walking out the door) with the Vessl bottle naturally in frame. Feeling first (calm, capable, on-track), product second.

## Self-contained image prompt (1:1 feed)

> Editorial lifestyle photo, natural daylight, airy and fresh. A 30-something person mid-motion in a bright modern apartment doorway, canvas tote on shoulder, holding a matte-finish smart water bottle with a subtle LED ring. Cool aqua and soft-blue palette, clean white surroundings, one warm coral accent (a scarf). Candid, not posed; shallow depth of field; condensation on the bottle. Lots of open space top-left for a headline and tagline, plus clear space bottom-left for a CTA button. No logos, no text in image.

*(Self-contained on purpose — the image tool has none of Claude Code's context, so the brand look, mood, and constraints are all baked in.)*

Paste the prompt into the AI image tool of your choice and generate it there. Nothing from the Claude Code session travels across with it — you carry the context between the two tools by hand.

## On-brand copy

- **Headline:** It keeps score, so you don't have to.
- **Tagline:** Hydration, handled.
- **CTA:** See how it works

Three lines, in that order, composited onto every frame. The CTA stays plain on purpose — the brief wants clicks to the launch page, and the brand voice rules out hype ("revolutionary," "game-changing") and pressure alike.

## Variant set (same concept, three frames)

Each variant is a **full standalone prompt**, not a delta off the first — the image tool has no memory of the previous run, so every prompt has to carry the whole brand look on its own.

**9:16 story/reel:**
> Editorial lifestyle photo, vertical 9:16 crop, natural daylight, airy and fresh. A 30-something person mid-motion in a bright modern apartment doorway, canvas tote on shoulder, holding a matte-finish smart water bottle with a subtle LED ring — subject placed in the lower third of the frame. Cool aqua and soft-blue palette, clean white surroundings, one warm coral accent (a scarf). Candid, not posed; shallow depth of field; condensation on the bottle. Generous open space across the top third for stacked text, plus clear space bottom-centre for a CTA button. No logos, no text in image.

**16:9 banner:**
> Editorial lifestyle photo, wide 16:9 crop, natural daylight, airy and fresh. A 30-something person mid-motion in a bright modern apartment doorway, canvas tote on shoulder, holding a matte-finish smart water bottle with a subtle LED ring — subject pushed to the right third, bottle sharp and in focus. Cool aqua and soft-blue palette, clean white surroundings, one warm coral accent (a scarf). Candid, not posed; shallow depth of field; condensation on the bottle. Open space across the left half for a headline and tagline, plus clear space bottom-left for a CTA button. No logos, no text in image.

Concept, palette, and message held constant; only the frame, the subject's position, and where the negative space sits change.

**Why every prompt ends "no text in image":** image tools render type unreliably and inconsistently across formats. Generate clean plates with the negative space reserved, then composite the headline, tagline, and CTA in your layout tool. That is how the required **"Hydration, handled."** tagline lands — and it keeps the copy pixel-identical across all three frames.

The composited result is in this folder as [`variant-1x1`](variant-1x1.png), [`variant-9x16`](variant-9x16.png) and [`variant-16x9`](variant-16x9.png) (`.html` alongside each `.png`). Same three lines of copy in all three, re-cut for the frame.

## Iteration note

There are two loops in this exercise, and a strong submission shows at least one of them properly.

**The prompt loop — across tools (illustrative).** This is the one the exercise asks for, and it needs an image tool to run:

> First generation came back high-contrast and staged — the mood read "gym ad," not calm/editorial. I revised the prompt to specify soft daylight, matte finish, candid framing, and open negative space, then ran it again in the image tool — the second pass looked like a real brand moment, not a stock fitness photo.

**The layout loop — in this folder (real, with both files).** Open [`first-pass-1x1.png`](first-pass-1x1.png) beside [`variant-1x1.png`](variant-1x1.png). The rejected pass turned the warm accent into a full coral wash, centred the bottle so the headline and CTA both landed on top of the product, set the type uppercase with a drop shadow, and left 32px margins in a brand whose mood is open space. The revision restored the white-and-aqua base with coral only on the CTA, moved the subject right of centre, dropped the type to sentence case, and tripled the margins.

The instructive part is that **the centred subject was causing the other faults.** With the bottle in the middle there was no legible home for the headline or the CTA, so both ended up over the hero. Reserve the negative space first, then set type into it — which is exactly what the prompts above are buying when they specify where the open space goes. A critique that names the *causing* fault is worth more than one listing four symptoms.

## Common mistakes

- A prompt that relies on context the image tool doesn't have ("use our brand colors") — must be spelled out.
- Three unrelated images instead of one concept in three frames.
- Re-rolling the same prompt instead of *revising* it (no real iteration).
- On-image copy that drifts clinical or fear-based, off the Vessl voice.
