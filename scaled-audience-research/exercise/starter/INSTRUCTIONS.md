# Run It at Scale, Then Find the Edge

Barkwell has a furniture-grade modern bed line it's close to launching and wants to know, at scale, what would stop people from buying it. Run 24–30 persona variants, write a findings report with an honest calibration disclosure — and notice where the surface you're working on stops being the right one for the job.

Work in Claude, using subagents to run your variants. Three templates are provided, one per stage:

- [`variant-generation-prompt.md`](variant-generation-prompt.md) — generate the variant set from your archetypes.
- [`response-collection-template.md`](response-collection-template.md) — the format every response lands in. **Set this up before you start running**, not after.
- [`aggregation-prompt.md`](aggregation-prompt.md) — turn the collected responses into ranked barriers and the by-segment cross-tab.

The templates cover generating, collecting and aggregating. Getting each variant to run in a genuinely isolated context — and proving it did — is the part they don't do for you.

Note the question here is different from the demo's: the demo asks *which feature is preferred*; this exercise asks *what would stop someone from buying*.

## What to produce

A structured findings report containing:

- The workflow you specified — the instruction you gave for running variants independently, **plus the evidence it actually ran that way**. Not the tool's summary of itself.
- A chart or table of aggregated barriers across 24–30 responses — the most common ranked, and how they differ across audience segments.
- A signal-vs-synthetic-consensus check: is the agreement real or manufactured?
- A **roster-bias audit**: which of your findings were decided by how you seeded the personas rather than by anything the responses revealed.
- A calibration disclosure: what this workflow can legitimately claim, what it can't, and what real-world validation would still be needed.
- A recommendation on which one or two barriers are worth acting on before launch, explicitly labeled directional.
- A short **surface note**: where this workflow started to strain, and whether you'd move it somewhere else.

## Requirements

- Ask for independent contexts — then **verify**. Both the tool's progress checklist and its own write-up will say "independent" whether or not it was, because both are prose it wrote. Find the run count your tool reports — the system's own record of what actually executed, not Claude's account of it — and check it against your variant count. A claim you didn't check isn't a finding.
- Generate enough variants for 24–30 responses; three personas run repeatedly is not a sample.
- **Audit your own roster.** Write down your archetype mix before you run, then read your barrier rankings against it and say, per finding, whether it tells you about the market or about who you asked.
- Watch how your variant prompts shape the answers. Instructing a persona to be "specific and personal" reliably produces specific, personal detail whether or not anything sits behind it — and it will land in your tally looking like data.
- Check signal against synthetic consensus. Judge whether your responses are real variation or one answer echoed back at you, and show what in the responses decided it. Read the spread and the outliers, not just the headline number.
- Note where the surface strains. Run at this scale, watch what it actually costs you to do it here, and report where the workflow starts to strain. Then say whether you'd keep it on this surface or move it to a scripted setup, and what decides that.

## Done when

Your report ranks the real barriers, shows **evidence** rather than assurance that the runs were independent, separates what your roster decided from what the responses revealed, and states plainly that the output is a hypothesis to validate, not a verdict. And you can say where this workflow's surface boundary sits, and why.
