# Worked Demo — Why Independence Is the Whole Game

*The real content: the finished walkthrough the demo produces.*

## Show the contamination first

Run 3–4 personas in a single shared chat and ask each which feature matters most. Watch the later "respondents" drift toward what earlier ones said. The apparent consensus is an artifact of shared context, not a finding. This is the failure the whole workflow exists to prevent.

## Reframe: one clean context per persona

True independence means each persona runs with **zero history** — the only way each response is a real, separate draw. In one chat, later variants anchor on earlier ones and the "sample" collapses into a single correlated stream.

## The workflow shape in Claude

Claude lets you orchestrate this: a variant list goes in, each variant runs in isolation, structured outputs come back, and you aggregate — repeatable and auditable. Past a handful of personas, opening a separate conversation for each one by hand stops being practical, and you lose the audit trail that proves they *were* separate.

1. Generate a small variant set (≈10) from the [`variant-generation-prompt.md`](../exercise/starter/variant-generation-prompt.md) template.
2. Run each variant as an independent call, no shared history.
3. Collect the responses into one aggregatable file.

## Tally, then interrogate

Aggregate to a quick number — whatever your top category comes to. Then stop and interrogate it: scale makes the number *look* like survey data, which is exactly the danger. Write the calibration disclosure line that must travel with it — what it can and can't claim.

## Key takeaway

Independence is the difference between synthetic research and synthetic theater. Speed and breadth come from the workflow; a real sample comes from isolated contexts; honesty comes from the calibration disclosure.
