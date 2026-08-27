# AI Marketer (C2) — Exercises & Demos

Source of truth for all demos and exercises in this course. **12 modules**, each with a filmed **demo** (instructor-led) and a hands-on **exercise** (learner self-assessed). Everything runs in **Claude Code**.

> **Internal doc — do not ship this README to learners.** Learners receive the exercise starter instructions and (after recording) the solutions. The demo briefs/walkthroughs and this guide are for the build team.

---

## Folder structure (what's actually here)

Each module folder is content-named and **unnumbered** (see the rule at the bottom). Inside every module:

```
<module>/
├── demo/                         # instructor-led walkthrough (filmed)
│   ├── starter/
│   │   ├── INSTRUCTIONS.md        # the demo BRIEF — what to record + why
│   │   └── <input assets>         # datasets / prompts the demo uses
│   └── solution/
│       ├── walkthrough.md         # the demo worked through, with reasoning
│       └── example-output.md      # the finished artifact the demo produces
│                                  #   (data modules: CSVs + chart PNGs instead)
└── exercise/                     # hands-on, learner self-assessed
    ├── starter/
    │   ├── INSTRUCTIONS.md        # the learner TASK — scenario, requirements, done-when
    │   └── <starter assets>       # datasets / prompts / templates provided
    └── solution/
        ├── SOLUTION.md            # worked answer key + Common Mistakes
        └── <output artifacts>     # data modules: forecast/LTV CSVs + charts
```

### What each file type is

| File | Audience | Purpose |
|---|---|---|
| `demo/starter/INSTRUCTIONS.md` | Instructor | The demo **brief**: setup, the beats to hit on camera, key takeaway |
| `demo/solution/walkthrough.md` | Instructor | The demo **worked through**, with the reasoning to narrate |
| `demo/solution/example-output.md` | Instructor | The **finished artifact** the demo produces (clean, no narration) |
| `exercise/starter/INSTRUCTIONS.md` | Learner | The **task**: scenario → What to produce → Requirements → Done when |
| `exercise/solution/SOLUTION.md` | Learner (post-record) | Worked **answer key**, one strong example, with Common Mistakes |
| `*.csv`, `*.png` | Both | Provided datasets (starter) and computed outputs (solution) |

> **Note on solutions:** on the `main` branch, `exercise/solution/` is an empty placeholder for the instructor to fill while recording. The `generated-solutions` branch contains generated worked solutions + demo outputs for review.

---

## The 12 modules (folder → skill → brand)

| # | Folder | Skill | Brand |
|---|---|---|---|
| SP1 | `goal-rich-briefing` | Goal-Rich Marketing Briefing | Flowline (freemium SaaS) |
| SP2 | `stress-test-strategy` | AI as Adversarial Reviewer | Flowline |
| SP3 | `evaluate-ai-tools` | AI Marketing Tool Evaluation | generic (copywriting) |
| SP4 | `synthetic-persona-interviews` | Synthetic Persona Design & Execution | Barkwell (dog beds) |
| SP5 | `synthetic-ab-test` | Synthetic A/B Testing Discipline | Barkwell |
| SP6 | `scaled-audience-research` | Scaled Synthetic Audience Research | Barkwell |
| SP7 | `cpa-cvr-forecast` | AI-Augmented Forecast Construction | Steep (DTC tea) |
| SP8 | `validate-forecast` | Forecast Validation & Calibration | Steep |
| SP9 | `ltv-to-bidding` | AI-Augmented LTV Forecasting | Steep |
| M6 | `claude-code-knowledge-work` | Marketing Knowledge-Work in Claude Code | Vessl (smart bottle) |
| M8 | `ai-generated-creative` | AI-Generated Marketing Creative | Vessl |
| M9 | `background-agent-research` | Single-User Agentic Delegation | Vessl |

Brands repeat within a family (Flowline, Barkwell, Steep, Vessl) but **no module references another** — each is self-contained so learners can enter at any point.

---

## What to review

- [ ] **Demo brief** reads as a recordable ~8–12 min segment; the beats land the key takeaway.
- [ ] **Exercise task** is clear: a learner knows what to produce, the requirements, and when they're done — without being handed a step-by-step recipe.
- [ ] **No spoilers** in exercise starters (the answer isn't stated in the task).
- [ ] **Solutions** are correct and, for the data modules, match the provided datasets.
- [ ] **Brand voice / scenario** is appropriate for a global audience.
- [ ] **Assets** referenced by each INSTRUCTIONS.md are present in the same folder.

---

## Open decisions (for Patrick / the author)

1. **SP5** — the A/B *demo* needs a senior-dog persona panel; only the furniture-grade panel (for the exercise) exists. Build one, or seed live on camera?
2. **SP9** — the cohort dataset uses real country codes (IN/CA/UK/US), engineered so India *looks* low-value until the confound is found. Keep, or switch to neutral region labels?
3. **M9** — pin the exact background-agent surface to teach/record.
4. **M8** — reframed from the dictionary's "Claude Design + Figma" to Claude Code + any image tool (Claude Design retired). Confirm.
5. **M6** — now Claude Code (not "Claude Chat"); dictionary title should update.
6. **SP7** — anchors on CPA, not the dictionary's "CPM" (agreed); dictionary wording to update.
7. **Demo file model** — demos currently carry brief + walkthrough + example-output; decide whether to keep all three or collapse to brief + output.

---

## Building & standards

The [Exercise Creation Resources](Exercise%20Creation%20Resources/) folder holds Udacity's guidelines:

- **[Exercise Guidance.md](Exercise%20Creation%20Resources/Exercise%20Guidance.md)** — exercise design, instruction writing, solution requirements. Primary reference.
- **[Accessibility Standards.md](Exercise%20Creation%20Resources/Accessibility%20Standards.md)** — WCAG 2.1 AA.
- **[Real-World Content Guidelines.md](Exercise%20Creation%20Resources/Real-World%20Content%20Guidelines.md)** — brands, trademarks, references (relevant to open decision #2).
- **[Third Party Images and Datasets.md](Exercise%20Creation%20Resources/Third%20Party%20Images%20and%20Datasets.md)** — licensing & attribution.

> ⚠️ **DO NOT NUMBER the exercises.** Modular content may be reused across programs where order and count differ, so folder names are content-named, not numbered. (The SP#/M# labels above are for this build's reference only.)
