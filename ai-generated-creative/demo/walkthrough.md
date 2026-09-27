# Worked Demo: Feed Claude Well, Then Generate

*The finished walkthrough the demo produces. It's a multi-tool workflow: Claude directs (concept, copy, prompt, critique), and an external AI image tool generates the actual picture. Claude has no image-generation of its own here, so you carry the context between the tools.*

## The quality of the creative is set by the inputs

AI makes it easy to generate creative fast, and just as easy to generate bad, off-brand creative fast. The difference is what you give Claude before you ask for anything. Start by assembling an input checklist:

- **Brand guide** ([`brand-guide.md`](../exercise/starter/brand-guide.md)), voice, color palette (with hex values), and typography.
- **Campaign brief** ([`creative-brief.md`](../exercise/starter/creative-brief.md)), objective, single message, mandatories.
- **Product and audience**, what it is and who it's for (both in the brief here).
- **User research** ([`user-research.md`](../exercise/starter/user-research.md)), what actually resonates, so Claude can calibrate, not just comply.
- **In-market creative** ([`in-market-creative-notes.md`](../exercise/starter/in-market-creative-notes.md)), what's working and what isn't, to emulate or avoid.
- **Channel**, an email hero, a paid social asset, and a website banner are different jobs; say which.

Not every project has all of these, but each one you add sharpens the concept and the prompt.

## Show the difference the inputs make

Give Claude only the brand guide and the brief first, and ask for a few concept directions, not one. The results are reasonable but generic, because that's all it knows. Then add the user research, the in-market notes, and the channel, and ask it to revisit. The concepts get calibrated: they lead with the feeling of an easier day rather than the tech, use the candid-real look the research says performs, and drop the guilt framing and spec-forward look that don't. The value of the extra inputs is that Claude can now justify its choices against evidence, not taste.

## Generate multiple, with self-contained prompts

Ask for the top two concepts, each as on-brand copy (headline, the "Hydration, handled." tagline, a short CTA) and a **self-contained image prompt**. Self-contained matters because the image tool has none of Claude's context: the full brand look (the palette by name and hex, the mood, the constraints) has to be written into the prompt itself. Generating two gives you options to react to rather than a single bet.

## Generate, then critique across tools

Take both prompts into the image tool and generate. These rarely land on the first try, and the skill is iterating on the prompt, not re-rolling. Bring the results back into Claude and have it critique them against the brand guide, the research, and the in-market notes. Because Claude has those inputs, the critique is calibrated: it can flag that a bottle's gradient is off the aqua/sky/white palette, or that the one warm accent landed on a bag strap instead of the CTA, not just say "make it pop." Carry the refined prompt back to the image tool and regenerate.

## The pairing

Claude holds the brand, the research, the concept, and the copy, and it can judge the output because you gave it the standard to judge against. The image tool executes. You assemble the inputs and carry the context between the tools.

## Key takeaway

Strong AI creative starts with strong inputs. Give Claude the brand, the brief, the research, what's working in market, and the channel; generate a few options rather than one; and tune against the standard you fed it, not against a vibe.
