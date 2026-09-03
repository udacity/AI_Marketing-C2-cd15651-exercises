# Sample Output — Rewrite Three, Compare Three

*Actual Claude output — each starter prompt run as-is, then rewritten via a goal-rich brief and re-run. One run; generative outputs vary run to run.*

---

## Prompt 1 — Checkout recovery — **over-prescribed**

**Naked run** (`Write a checkout-recovery email. Exactly four sentences. Open with a question. Mention our 20-percent-faster workflow. Add a countdown timer. End with a P.S.`):
> Ready to work 20% faster? You were about to upgrade to Flowline Premium, but your checkout is still waiting. Complete it in the next 24 hours — ⏳ 23:59:00 — and put that faster workflow to work today. P.S. We saved your cart, but this reminder won't last long!

*Mechanically correct, but it obeys arbitrary rules instead of speaking to the reader — fake countdown, forced 20% mention, no real reason.*

**Goal-rich brief:** reached the annual-Premium payment screen and left · goal: return to checkout · context: already chose to upgrade, stopped at payment · constraints: no discount, no fake urgency, don't re-explain the product, short · success: clicks back to the checkout page.

**Rewritten run:**
> **Subject:** You were one step from Premium
> Hi [First name], you'd reached the last step of upgrading to Flowline Premium (annual) when something got in the way — it happens. **[Return to checkout →]**

**Element that changed the output most:** *Audience* — naming "already at the payment screen" flipped it from a generic re-explainer into a low-friction "pick up where you left off" nudge.

---

## Prompt 2 — New-user activation — **under-specified**

**Naked run** (`Write an in-app message for new users.`):
> 👋 Welcome to Flowline! We're glad you're here. Take a look around and explore everything Flowline has to offer — and reach out if you need a hand. Happy organizing!

*Generic welcome; no stage, no action.*

**Goal-rich brief:** free user ~3 days in, no first project yet · goal: create first project · context: hasn't reached the product's value yet — this is the activation moment · constraints: one CTA, short, in-app, no feature dump · success: completes the first project, not just opens the app.

**Rewritten run:**
> You're almost set up. Create your first project to see how Flowline keeps your work moving. **[Create a project]**

**Element that changed the output most:** *Goal* — pinning the single next action turned a vague welcome into a one-CTA push toward first value.

---

## Prompt 3 — Power-user referral — **vague**

**Naked run** (`Make our best users feel appreciated.`):
> 💙 Thank you for being one of our favorite Flowline users! We appreciate everything you do. You're the best!

*No task, no action — pure sentiment.*

**Goal-rich brief:** paying users who log in weekly and use Flowline heavily · goal: a referral ask · context: they already get real value — appreciation is the frame, the referral is the ask · constraints: don't over-incentivize, keep it warm not transactional · success: a qualified referral, not just a warm feeling.

**Rewritten run:**
> **Subject:** You get more out of Flowline than almost anyone
> Hi [First name] — you're one of our most active users, and it shows. If Flowline's become part of how you work, someone you know would probably get the same value from it. Know a good fit? **[Send them an invite]** — no strings, just passing on something useful.

**Element that changed the output most:** *Goal* — converting fuzzy sentiment ("feel appreciated") into a concrete referral ask gave the model something to actually drive toward.

---

*Each fix was different: prompt 1 **lost its rules** — five arbitrary mechanics cut, a real audience named; prompt 2 gained a specific goal; prompt 3 gained a task where there was none.*
