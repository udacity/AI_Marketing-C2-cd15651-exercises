# Worked Demo — Score One Tool Against the Framework

*The finished walkthrough the demo produces. Evaluating a new software platform requires looking past a glossy vendor presentation to determine if a tool actually fits your team's real needs.*

In this demo, a lean startup with two people covering lifecycle and email evaluates a fictional AI email copywriter called **Draftwell**. The scored output is in [`example-output.md`](example-output.md).

## The six dimensions

| Dimension | The question it answers |
| --- | --- |
| Capability fit | Does it do your specific job well? |
| Fit with your stack | Does it connect to tools you already run? |
| Cost vs. value | Is the price justified by the impact? |
| Data & privacy | Where does your data go? |
| Learning curve | How hard is it to adopt? |
| Brand-voice control & brand safety | Can you keep output on-brand and compliant? |

Because Draftwell is fictional, the demo asks Claude to simulate pilot data. In real life, you engage directly with the product in a pilot or a free trial and collect real evidence to score against your rubric.

## How to score a tool and read the scores

**1. Score against your own framework.** You give the AI your team context, the product details, and the six dimensions, and ask for a score with a one-line rationale on each. To get a baseline evaluation, try a prompt like this:

> Can you simulate data/insights from a Draftwell pilot, and evaluate that pilot against these specific criteria: capability fit, fit with your stack, cost versus value, data and privacy, learning curve, and brand-voice control and brand safety. Provide brief evaluations (incl. a 1 out of 5 score, 5 being best) for each.

**2. Challenge the AI's score with your own judgment.** Review the rationale behind every number and push back where a score feels unearned. Cost versus value is the likely one here: you might push it down from 4 to 3, because time saved is not yet business impact.

| Dimension | AI score | Check before you accept it |
| --- | --- | --- |
| Capability fit | 4 | Does it hold up on nuanced copy? |
| Fit with your stack | 4 | Does it reach the tools where briefs and reviews live? |
| Cost vs. value | 4 | Can you point to business impact, not just hours saved? |
| Data & privacy | 3 | Are retention and deletion terms clear? |
| Learning curve | 5 | Could your team adopt it quickly? |
| Brand-voice control & brand safety | 3 | Would you ship it without a heavy edit? |

**3. Let your context change what matters.** Your context sharpens the read rather than changing the scores. For a lean team that cannot build its own tools, fit with your stack and learning curve matter more. Data and privacy and brand-voice control become go/no-go questions. To see how a lean team changes the weighting, a request like this works well:

> We are a lean org. We don't have a lot of product or engineering resources to develop internal AI tooling, but we also don't have much support for copywriting.

**4. Make your own call.** The AI tool will not make the final business decision for you. Total the adjusted scores, ask whether you could build the capability in-house, and make your own adopt, pilot, or pass call based on the tradeoffs you can accept.

## Key takeaway

You score a tool against a framework that reflects your real needs, react with your own judgment, and always check build versus buy before you spend.

**Try it:** Score one tool your team is considering on the six dimensions, then mark the one score you would push back on and why.
