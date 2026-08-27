# A/B Test — Aggregation Prompt

*Provided template. After you've scored every persona, paste all the scored outputs into Claude with this prompt to produce a ranked recommendation with confidence and stated limits.*

---

```
I ran a synthetic A/B test of three creative directions across a panel of personas.
Their scored outputs are pasted below.

Please:

1. Build a summary table: Persona | Direction A total | Direction B total |
   Direction C total | Top pick.

2. Calculate the average total for each direction across all personas.

3. Calculate the average score per dimension (Resonance, Believability, Relevance,
   Distinctiveness) for each direction.

4. Identify:
   - The winning direction overall.
   - The runner-up and the margin.
   - Any direction that was strong for one persona but weak for another (a split panel).
   - The dimension where the winner scored highest, and where it was most vulnerable.

5. Produce a ranked recommendation in this format:

RANKED RECOMMENDATION
Winner: [direction] — avg [X]
Strongest dimension: [name — avg]
Most vulnerable dimension: [name — avg]
Runner-up: [direction] — avg [X], margin [X]
Third: [direction] — avg [X]
Notable panel splits: [any direction that divided the panel]
Confidence level: [High / Medium / Low]
Basis for confidence: [1-2 sentences]
Stated limits:
- [e.g., a small synthetic panel is directional, not statistically significant]
- [e.g., brief descriptions, not finished creative]
- [e.g., synthetic responses over-weight reasoning vs gut reaction]

SCORES:
[Claude reads the scores you paste below.]
```

---

**What to do with the output:** the winner becomes your recommended direction, but pair it with the confidence and limits. Watch for a direction that wins overall while polarizing the panel; that's a targeted play, not a safe default.
