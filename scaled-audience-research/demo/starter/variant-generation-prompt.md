# Scaled Research — Variant Generation Prompt

*Provided template for the scaled synthetic audience research workflow. Use it to generate many distinct persona variants across your archetypes, so your sample spans the real audience instead of asking the same few personas repeatedly.*

---

```
I am running scaled synthetic audience research for [BRAND / PRODUCT]. I have defined
[N] core archetypes. For each archetype, generate [NUMBER] distinct variants.

ARCHETYPES:
1. [Archetype name] — [2-3 sentences: who they are, their situation, their primary
   reason to care about this product]
2. [Archetype name] — [...]
3. [Archetype name] — [...]

VARIANT INSTRUCTIONS:
Each variant should:
- Share its archetype's core profile (same general situation and primary driver).
- Differ in: age (within a 15-year range), location, specific circumstances, and one or
  two personality traits that would affect how they react to a product or message.
- Feel like a real, distinct person, not a slight rename of the same character.
- Be described in 4-6 sentences.

FORMAT (for each variant, clearly labeled):
Variant [number]: [First name]
Archetype: [which archetype]
Age:
Location:
Profile: [4-6 sentences]
Key need: [one sentence]
```

---

**Why variants, not repeats:** running the same three personas a hundred times gives you one correlated opinion, not a sample. Generating structured variants across attributes is what lets a scaled read actually span your audience.

**Independence note:** when you run these variants, each should respond in its own clean context. If they all answer in one shared conversation, later variants anchor on earlier ones and your "sample" collapses into a single stream. Run them isolated (this is why the exercise uses Claude Code to orchestrate the runs).
