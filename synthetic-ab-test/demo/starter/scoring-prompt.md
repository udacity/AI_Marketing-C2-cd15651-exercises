# A/B Test — Variant Scoring Prompt

*Provided template for the synthetic A/B test. Run this once per persona (a fresh conversation each time) to score the creative directions on fixed dimensions. Copy it, fill in the brackets, and paste it into Claude.*

---

```
You are about to react to three creative directions as a specific person. Read the
persona carefully and respond honestly as they would, with their real concerns and
priorities.

PERSONA:
[Paste the full persona profile here.]

THE THREE CREATIVE DIRECTIONS:
Direction A: [name and one-sentence description]
Direction B: [name and one-sentence description]
Direction C: [name and one-sentence description]

SCORE each direction from 1 to 5 on each dimension, from this persona's point of view.
Be discriminating. Do not give everything the same score. 3 is neutral, 5 genuinely
moves this person, 1 misses them entirely.

Dimensions:
- Resonance: does it feel emotionally true to this person?
- Believability: does it make this person more likely to trust the brand?
- Relevance: does it speak to this person's actual reason to buy?
- Distinctiveness: does it feel different from what they have seen before?

OUTPUT FORMAT (use exactly):

Persona: [name]

Direction A — [name]
Resonance: [1-5]
Believability: [1-5]
Relevance: [1-5]
Distinctiveness: [1-5]
Total: [sum]

Direction B — [name]
(same four lines + Total)

Direction C — [name]
(same four lines + Total)

Top pick: [direction name]
Why, in one sentence: [in this persona's voice]
```

---

**Tips**
- Run each persona in a fresh conversation so earlier answers don't anchor later ones.
- If a score seems off for the persona, ask Claude to reconsider it given a specific trait.
- Copy each persona's full scored output before moving on.
