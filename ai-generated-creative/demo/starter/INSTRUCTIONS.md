# Demo — Direct the Concept, Then Generate It

*Instructor demo brief. Estimated running time ~10 minutes. The full worked version is in [`../solution/walkthrough.md`](../solution/walkthrough.md).*

## Setup

- **Scenario:** Vessl needs on-brand social and ad creative for its launch. Claude Code is the creative director; an AI image tool is the executor.
- **Tools:** Claude Code (creative direction, prompts, copy) + an AI image tool.
- **Inputs:** [`brand-voice-guide.md`](brand-voice-guide.md) and [`creative-brief.md`](creative-brief.md).

## What the demo demonstrates

1. From the brand-voice guide and creative brief, have Claude act as creative director: propose one concept, then write a **self-contained image prompt** (baking in brand look, mood, constraints — the image tool has none of Claude's context) plus on-brand copy.
2. Take that prompt into an image tool and generate the visual.
3. Run the critique loop across tools: bring the image back into Claude, ask for specific feedback against the brand and brief, carry the refined prompt back, regenerate.
4. Adapt across formats: have Claude rework the prompt and copy for a different aspect ratio, keeping concept and brand consistent.
5. Show the pairing: Claude holds the brand, concept, and copy; the image tool executes. You direct, and you carry the context between them.

## Key takeaway

Great AI creative comes from strong direction, disciplined iteration, and carrying your context between tools — not from one magic surface.
