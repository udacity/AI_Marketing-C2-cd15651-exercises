# Demo Output: Feed Claude Well, Then Generate

*Illustrative Claude output for the input-checklist demo. Direction-only: the images are generated live in an external image tool and are not included here. One run; outputs vary. Shown as generic placeholders since a live run differs each time.*

## First pass (brand guide + brief only)

**Prompt:** `From the brand guide and creative brief, give me three concept directions off the single key message. One-line concept, headline, tagline each.`

**Output (reasonable but generic):**
> 1. **The Silent Assistant**, it's already handled in the background. *"It's already on it."*
> 2. **The Streak You Didn't Try For**, effortless consistency. *"Turns out you're winning at this."*
> 3. **One Less Tab Open**, against the mental load. *"One less thing on your mind."*

## Second pass (after adding user research + in-market notes + channel)

**Prompt:** `I've added user-research.md and in-market-creative-notes.md; this set is for the paid social feed. Revisit and rank the concepts: lead with feeling, use the candid-real look that's performing, avoid guilt framing and the spec-forward look. Say why the top one fits the research and the in-market pattern.`

**Output (calibrated, and now justified):** the concepts sharpen toward the ordinary "already-handled" moment, cite the candid morning-routine pattern the notes flag as working, and drop anything tech-forward or guilt-based. The top pick is defended against the research and the in-market notes, not taste.

## Multiple self-contained prompts

For the top two concepts, Claude produces on-brand copy (headline, the "Hydration, handled." tagline, a short CTA) and a self-contained 1:1 image prompt that bakes in the palette by name and hex (Vessl Aqua `#16B1C7`, Sky `#8FD2E3`, Marine `#12414E`, white/Mist base, Coral `#FF7A59` for the CTA), the candid daylight look, and clear negative space for the type. Type is composited afterward (`no text in image`), because image tools render type unreliably.

## Critique across tools

Both prompts are generated in the image tool, then brought back for a critique against the brand guide, the research, and the in-market notes. Because Claude has those inputs, the critique is calibrated: it can flag an off-palette bottle gradient or a warm accent that landed somewhere other than the CTA, then produce a revised prompt that fixes the specific miss.

**The cross-tool point:** everything is baked into the prompt precisely because the image tool won't remember what Claude knows. Writing the self-contained prompt, and feeding Claude enough to judge the result, is the craft.
