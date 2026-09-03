# AI Marketer (C2) — Exercises & Demos

Source of truth for all demos and exercises in this course. **12 modules**, each with a **demo** (a worked demonstration the learner watches) and a hands-on **exercise** (learner self-assessed). Everything runs in **Claude Code**.

> **Internal doc — do not ship this README to learners.** Everything else is learner-facing: the demo is watched, the exercise starter is the task, and the solution is shown after. Only this README is for the build team.

---

## Folder structure (what's actually here)

Each module folder is content-named and **unnumbered** (see the rule at the bottom). Inside every module:

```
<module>/
├── demo/                          # worked demonstration (flat — no subfolders)
│   ├── walkthrough.md             # the demo worked through
│   └── example-output.md          # the finished artifact it produces
│                                  #   (data modules: CSVs + chart PNGs)
└── exercise/                      # hands-on, learner self-assessed
    ├── starter/
    │   ├── INSTRUCTIONS.md         # the TASK — what's expected (scenario, requirements, done-when)
    │   └── <assets>                # datasets / prompts / templates provided
    └── solution/
        ├── walkthrough.md          # the worked solution + Common Mistakes
        └── example-output.md       # a sample output (data modules: CSVs + charts)
```

### What each file type is

| File | Purpose |
|---|---|
| `demo/walkthrough.md` | The demo **worked through** — what the learner watches demonstrated |
| `demo/example-output.md` | The **finished artifact** the demo produces (data modules: CSVs + chart PNGs) |
| `exercise/starter/INSTRUCTIONS.md` | The **task**: scenario → What to produce → Requirements → Done when |
| `exercise/solution/walkthrough.md` | The **worked solution** (one strong example) + Common Mistakes |
| `exercise/solution/example-output.md` | A **sample output** — the clean deliverable (data modules: CSVs + charts) |

All of the above is learner-facing (demos are watched; solutions are shown on the solution page). Only this README is internal.

> **Note on solutions:** `exercise/solution/` on `main` holds generated worked solutions + demo outputs for review. They are AI-generated stand-ins to be replaced with real on-screen output at recording — see [AUTHOR_NOTE.md](AUTHOR_NOTE.md).

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

- [ ] **Demo walkthrough** reads as a recordable ~8–12 min segment and lands the key takeaway.
- [ ] **Exercise task** is clear: a learner knows what to produce, the requirements, and when they're done — without being handed a step-by-step recipe.
- [ ] **No spoilers** in exercise starters (the answer isn't stated in the task).
- [ ] **Solutions** are correct and, for the data modules, match the provided datasets.
- [ ] **Brand voice / scenario** is appropriate for a global audience.
- [ ] **Assets** referenced by each INSTRUCTIONS.md are present in the same folder.

---

## Open decisions (for Patrick / the author)

1. ~~**SP5** — the A/B *demo* needs a senior-dog persona panel.~~ **Resolved:** provided at `synthetic-ab-test/demo/persona-panel-senior-dog.md` (Eleanor / David / Marcus, mapped to the three angles). Related: the SP4 persona-interview demo was missing its senior-dog research asset after the demo/exercise split; now provided at `synthetic-persona-interviews/demo/research-snippets-senior-dog.md`.
2. **SP9** — the cohort dataset uses real country codes (IN/CA/UK/US), engineered so India *looks* low-value until the confound is found. Keep, or switch to neutral region labels?
3. ~~**M9** — pin the exact background-agent surface.~~ **Resolved:** it is a **Claude Code subagent** (`.claude/agents/*.md`). Starter agent definition + invocation now provided; demo/solution scope aligned to the water-bottle market.
4. ~~**M8** — reframed from the dictionary's "Claude Design + Figma" to Claude Code + any image tool.~~ **Resolved (confirmed):** Claude Code + any image tool. Dictionary title/wording to follow.
5. ~~**M6** — now Claude Code (not "Claude Chat").~~ **Resolved (team decision):** the course standardizes on **Claude Code**, and M6 teaches the persistent-workspace idea via a **project folder + `CLAUDE.md` + files on disk**, not chat "Projects." Assets were audited and already use Claude Code language (project folder / workspace / `CLAUDE.md`), with no chat-"Projects"/"project knowledge"/"upload" phrasing. **Team to-do:** update the module dictionary title (M6 "Claude Chat" → Claude Code) and make sure any classroom/course-level copy uses "project folder," not chat "Projects," so the surface language matches.
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
