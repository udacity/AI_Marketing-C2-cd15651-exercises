# Demo Output — Set Up a Project Workspace, Build a Review-Response Kit

*Actual Claude output — the review-response kit Claude Code produced from the brand-voice guide + week-1 reviews in the project folder (nothing pasted into the prompt). One run; outputs vary.*

---

## 1. The playbook

**Prompt:** `Using the brand-voice guide and the week-1 reviews in this project, build our review-response playbook.`

**Claude Code's output → `response-playbook.md`** (after the refinement pass that added the escalation tier):

> # Vessl — Review Response Playbook
>
> **The voice, applied to replies:** talk to one person as "you." Short, plain sentences. Thank them for the specific thing they said, not for "their feedback." Encouraging, never nagging. Clear, never clinical. A little wit only where the review is already light.
>
> **Four tiers**
>
> | Tier | Looks like | Reply does |
> |---|---|---|
> | **Praise** | R-101, R-105 | Name the specific win they mentioned. One line, no upsell. |
> | **Qualified praise** | R-102, R-104 | Lead with what worked, then answer the gripe plainly and say what happens next. |
> | **Complaint** | R-103 | Own it in the first sentence. Give the fix or the workaround. Never explain it away. |
> | **Escalation** | R-106 | Move it off the public thread. Support does not improvise a refund in public. |
>
> **Never say:** "we're sorry you feel that way" • "as per our policy" • anything spec-sheet ("sensor telemetry," "fluid-intake analytics") • anything that implies the customer got it wrong • anything about being dehydrated.
>
> **Always:** reply as a person, not the brand. Under 60 words. One concrete next step where there is one.

## 2. The replies

**Prompt:** `Draft replies to all six week-1 reviews, following the playbook.`

**Claude Code's output → `replies-week-1.md`** (3 of 6 shown):

> **R-101 (praise)** — "Every day for two weeks is a real streak — nice work. Forgetting to log was exactly the thing we wanted to delete, so it's good to hear it's gone quiet in the background for you."
>
> **R-103 (complaint)** — "A soaked notebook is on us, not on you. The lid seal needs a firm quarter-turn to seat, and if yours still weeps after that, it's a faulty lid and we'll send a new one — reply here and we'll sort it. You shouldn't have to think about whether it's safe in a bag."
>
> **R-106 (escalation)** — "Two units failing the same way isn't a pattern you should have to keep testing for us. A refund is absolutely reasonable, and it's yours — I've sent you a direct message so we can do it without you repeating the story again."

## 3. The themes digest

**Prompt:** `What's actually recurring across this batch, and what belongs with the product team rather than support?`

**Claude Code's output → `review-themes.md`:**

> **Recurring — product, not support**
> 1. **Tracking stops or under-reports** (R-102 history loss, R-104 silent sensor, R-106 two dead units). Three of six reviews. The reliability of the core promise is the top theme.
> 2. **The app can't distinguish "needs charging" from "not reporting"** (R-104, and probably the root of R-106). One screen state for two very different problems.
> 3. **Lid seal seats without feeling seated** (R-103). One report, but a bag-of-water outcome.
>
> **Support can close on its own:** R-101, R-105 (praise), R-102's history restore.
>
> **Watch:** the praise and the complaints agree on the same thing — people judge Vessl on whether the tracking is quietly correct. Every complaint here is a reliability complaint wearing a different hat.

## 4. Next week, fresh session

Session closed. `customer-reviews-week-2.md` dropped into the same folder a week later, folder reopened.

**Prompt:** `New reviews just landed in this folder. Draft replies using the playbook.`

**Claude Code's output → `replies-week-2.md`:**

> **R-107 (qualified praise)** — "'Doesn't nag' is the review we most want, so thank you. You're right that the seal doesn't announce itself — firm quarter-turn until it stops, and we've passed the it-should-be-obvious point along, because it should be."
>
> **R-108 (praise)** — "Three months and still on the desk is the only benchmark we care about. Glad it earned its spot."
>
> **R-109 (complaint)** — "Drifting after a refill and needing a re-calibrate every couple of days isn't the deal. Recalibrate once more so we have a clean baseline, then reply here — this is one for our product team, not a setting you should have to keep fixing."
>
> **Claude Code flagged, unprompted:** *R-109 is theme 1 from `review-themes.md` — tracking reliability — now on its third distinct failure mode.*

**Grounding to point out on camera:** week two took one prompt. The tiers, the word limit, the never-say list and the standing themes were all read back off disk — the playbook written the previous session was still governing the replies, and the reviews were still being matched against a themes file nobody re-explained.
