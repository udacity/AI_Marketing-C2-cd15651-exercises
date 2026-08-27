# Demo — Why Independence Is the Whole Game

*Instructor demo brief. Estimated running time ~10 minutes. The full worked version is in [`../solution/walkthrough.md`](../solution/walkthrough.md).*

## Setup

- **Scenario:** Barkwell wants to know which single feature matters most to buyers, at scale.
- **Tool:** Claude Code (to orchestrate independent per-persona runs).
- **Input:** the [`variant-generation-prompt.md`](variant-generation-prompt.md) template.

## What the demo demonstrates

1. Run 3–4 personas in a single chat and point out the anchoring/drift in later responses — apparent consensus that's an artifact, not a finding.
2. Reframe: each persona must run with zero context bias. Show the workflow shape in Claude Code — variant list in, isolated run per persona, structured output out.
3. Generate a small variant set (e.g., 10) from the template.
4. Run them as independent calls and collect responses into one aggregatable file.
5. Tally into a quick "62% prefer X" number — then interrogate it and write the calibration disclosure line that must travel with it.

## Key takeaway

Independence is the difference between synthetic research and synthetic theater. The workflow gives you speed and breadth; isolated contexts give you a real sample; the calibration disclosure keeps you honest about what it still is — a directional prior, not a measurement.
