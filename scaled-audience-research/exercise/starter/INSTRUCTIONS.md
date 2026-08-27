# Build the Workflow, Find the Barriers

Barkwell has a furniture-grade modern bed line it's close to launching and wants to know, at scale, what would stop people from buying it. Build a Claude Code workflow that runs 100+ persona variants in independent contexts, surface the top barriers to purchase, and write a findings report with an honest calibration disclosure.

Work in Claude Code. Use the [`variant-generation-prompt.md`](variant-generation-prompt.md) template to generate your variants.

Note the question here is different from the demo's: the demo asks *which feature is preferred*; this exercise asks *what would stop someone from buying*.

## What to produce

A structured findings report containing:

- The workflow you built, including how you enforced independence (no shared history between variants).
- A chart or table of aggregated barriers across 100+ responses — the most common ranked, and how they differ across audience segments.
- A signal-vs-synthetic-consensus check: is the agreement real or manufactured?
- A calibration disclosure: what this workflow can legitimately claim, what it can't, why independent contexts matter, and what real-world validation would still be needed.
- A recommendation on which one or two barriers are worth acting on before launch, explicitly labeled directional.

## Requirements

- Each variant must run in an **independent context**. If they share history, later variants anchor on earlier ones and your sample collapses — enforcing isolation is the core of the exercise.
- Generate enough variants for 100+ responses; three personas run repeatedly is not a sample.
- Check signal against synthetic consensus: genuine signal shows variation and dissent; manufactured consensus looks like everyone saying the same thing in nearly the same words. Look at the spread and the outliers, not just the headline number.
- The calibration disclosure is required, not optional. A scaled number that looks like survey data is exactly what needs the disclosure.

## Done when

Your report ranks the real barriers, shows how independence was enforced, distinguishes genuine signal from manufactured consensus, and states plainly that the output is a hypothesis to validate, not a verdict.
