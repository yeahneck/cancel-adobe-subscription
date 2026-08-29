---
name: cancel-adobe-subscription
description: Cancel an individual Adobe subscription - Creative Cloud (All Apps or a single app such as Photoshop, Illustrator, Premiere Pro, Lightroom), Acrobat, Photography plan, Adobe Stock - and ask Adobe support to waive the early-termination fee (ETF). Use whenever the user wants to cancel, stop, end, quit, or get out of an Adobe plan, asks what Adobe would charge them to cancel, says Adobe wants a fee to cancel, or wants an Adobe cancellation fee refunded. Also use to work out first which Adobe plan type they have (monthly, annual paid monthly, prepaid, inside the 14-day window, app-store or Teams billing). Not for using, installing, or troubleshooting Adobe apps, and not for Teams/Enterprise Admin Console contracts beyond pointing the user to the right place. Never confirms a charge, fee, plan switch, or cancellation without the user's explicit yes.
license: "PolyForm-Noncommercial-1.0.0 (https://polyformproject.org/licenses/noncommercial/1.0.0). Required Notice - Copyright yeahneck (https://github.com/yeahneck)"
compatibility: Requires a browser tool the agent can drive (any). Optional read access to the user's mailbox speeds up the one-time passcode and confirmation e-mails; not required.
metadata:
  author: yeahneck
  version: "1.0.0"
  verified: "2026-08"
---

# Cancel an Adobe subscription, asking for the fee to be waived

As of August 2026, on EU individual plans, Adobe's "annual plan, paid monthly" contracts charge an **early-termination fee (ETF) of 50% of the remaining months** if cancelled on the website after the first 14 days. A **human support rep can waive it** — it's their discretion, not policy — and in the author's runs did so as a "one-time exception" when asked plainly. This skill gets to that human and asks correctly, with the user in control at every step that touches their identity, their money, or their account.

## Hard rules

1. **Never confirm any charge, fee, offer, or plan switch without a fresh, explicit yes from the user for that exact amount.** A general "cancel it for me" is not consent to pay a fee. Stop at any screen showing a money amount and ask.
2. **Never type passwords, one-time passcodes, card numbers or any part of them, or billing/address details.** Login and the support-chat OTP are the user's job; if the rep asks for verification data, hand off to the user. Wait for "done", continue.
3. **Decline every retention offer** ("2 months free", "switch plans", "40% off"). They extend or restart the contract.
4. **Support chat first, self-serve last.** Use the website's cancel flow only when its fee screen shows 0 or the user has explicitly accepted the fee.
5. **Nothing gets cancelled without the user's yes — even at zero cost.** Before the final step of either route, say exactly what is about to happen (*"‹plan› will be cancelled, ends ‹date›, ‹fee or nothing› charged — go ahead?"*) and wait. Self-serve: that's the review screen. Chat: that's before you send the lock-in line, because the rep finalizes right after it — and equally before the end-of-term fallback if the waiver is refused.
6. **Relay every message from Adobe's rep to the user verbatim, and show the user any message you intend to send that is not in [references/chat-script.md](references/chat-script.md) before sending it.**
7. **Say nothing on the user's behalf that the user hasn't said.** The script's brackets are for the user's own reason for cancelling — ask, and use their words, or leave the clause out. Never assert the user's finances, usage, or status to the rep from your own inference.
8. **Labels below are what was seen in August 2026, not a contract.** Adobe changes and A/B-tests this funnel. If a label differs, match the *goal* of the step to an option whose effect is obvious and reversible (a menu choice, "continue", a category); if nothing clearly matches, or the step is consequential (anything that could confirm, cancel, accept, or pay), stop, describe the screen, and ask the user. Never click a button whose effect you are inferring.

## Step 0 — Login and account check

Open `https://account.adobe.com/plans` and look at what loaded:

- **Login page** (Adobe often forces re-authentication): ask the user to log in in that tab and say "logged in". Do not type credentials or click SSO buttons on their behalf.
- **Plans page already showing** (session was live): stop. Read exactly one thing — the signed-in e-mail from the avatar menu top-right — and say: *"Adobe is already signed in as ‹e-mail›. Is that the right account? Say continue."* Touch nothing else until they do. If it's the wrong account, the user signs out and back in themselves. In a cloud browser the user can't see the page, so echoing the e-mail is the whole check.

## Step 1 — Inventory and plan-type triage (2 min)

On `/plans`, for each plan card record: product, price/month, currency, **Next payment** date, **"Annual plan, paid monthly"** vs monthly. Open **Manage plan**: note **"Subscribed since"** (the day-of-month is the anniversary; the current term ends 12 months after the last anniversary) and whether the End-service box says **Adobe no longer offers this plan**.

Report per plan, e.g.: *Photography plan, €15.12/mo, subscribed since 2024-12-05 → term ends 2026-12-04 → 3 months left → €45 to ride out → ETF ≈ €23.* Add the waiver arguments **that are true from what the page shows**: discontinued plan, promo price that expired mid-term. (Whether the user still uses it, or why they're cancelling, is theirs to say — see rule 7.)

If the user bought on a VAT ID, statutory consumer withdrawal rights may be reduced or unavailable — it depends on whether the purchase was for business purposes and the rules differ by country (some, including Poland, still protect sole traders for purchases outside their line of work). Don't advise on it; note it and move on. The chat route works either way.

**Plan-type triage** — the chat-waiver route is for one case; the others are quicker or elsewhere:

| What the plan card / Manage dialog shows | Do |
|---|---|
| **Annual plan, paid monthly** — the verified case | Step 2 (support chat, ask for the waiver) |
| **Monthly** (no commitment) | No fee exists. Fast path: Step 3 directly, confirm the screen shows 0, one "go ahead?" to the user. Skip the chat. |
| **Annual, prepaid** (one yearly charge) | No termination fee, but Adobe's policy gives no refund after 14 days — cancelling only stops the renewal. Tell the user; if they still want it, Step 3 (fee screen shows 0). Chat can't improve on this. |
| **Purchased within the last 14 days** | Adobe's published policy is a full refund on new orders inside 14 days; a renewal may not reset it. Step 3, read the screen, proceed only on what the screen actually says, one "go ahead?" to the user. |
| **"Managed by Apple / Google"**, or billed through an app store | Adobe cannot cancel it. Send the user to the store's subscription page (iOS: Settings → Apple ID → Subscriptions; Android: Play Store → Payments & subscriptions). Stop here. |
| **Teams / Enterprise** (Admin Console, not account.adobe.com) | Out of scope — an admin-console contract with its own support path. Say so and stop. |
| **Adobe Stock** | Same annual-paid-monthly mechanics, unverified; run Step 2 and expect the rep to also mention unused credits. |

**Stop here.** Show the per-plan report and ask which plans to cancel, and ask for the user's own reason in their words (or none). Do not open the support chat or the cancel flow for any plan the user has not named.

## Step 2 — Support chat (the path where the fee can be waived)

1. Go to `https://helpx.adobe.com/contact.html` (Adobe redirects to the account's locale), click the chat bubble (bottom right). Non-English regions: "chat available only in English" → **Continue in English**.
2. **Goal: get from the bot to a human in the billing queue.** The bot loops unless steered. Path seen in August 2026 (labels may differ; rule 8):
   - type `Talk to a human agent` (synonyms it also understands: "agent", "human", "representative")
   - confirm when it asks → **Yes, chat with an agent**
   - asked to describe the issue → `Billing: cancelling my <plan> and asking about the early termination fee`
   - if it offers categories → the closest to **Billing / Payment**, reached via **Something else** if needed. Avoid any "Cancel a plan" category; it routes back to self-serve links, not a person.
   - "Connecting you to an agent" → queue typically 3–10 min. Wait 60–90 s between checks; do not restart. You have reached a human when a named person greets you and the "AI-generated responses" footer is gone.
3. While queued, post the **case message** from [references/chat-script.md](references/chat-script.md), filled only with the account e-mail shown on the plans page, the plan name, the page-verified arguments, and the user's own reason. It asks for options and the waiver and says not to process anything yet — it is not a cancellation instruction.
4. When the rep joins, follow the script in order: decline the retention offer; if the ETF is stated without a waiver, ask for a one-time exception once. Relay everything (rule 6).
5. When the rep says a one-time passcode was e-mailed: stop and tell the user (*subject: One Time Passcode for Account Verification*, usually within a minute). The user types it into the chat. If you can read the mailbox, you may say it has arrived — never read out or enter the code. No passcode after 3 minutes: ask the user to check spam, then ask the rep to resend once; after two failures, ask the rep to note the case and end the chat — do not proceed by any other verification.
6. **Gate (rule 5):** tell the user *"The rep is ready to cancel ‹plan› with the fee waived, ends ‹date›, nothing charged — go ahead?"* and wait for yes. Only then send the **lock-in** line and wait for **"That is correct."**
7. If the waiver is refused twice: **gate again** — *"The rep won't waive the fee. The alternative is cancel at end of term (‹date›), no further charges, plan usable until then — go ahead?"* Only on yes send the end-of-term line from the script.
8. After "The plan has been successfully cancelled": send the close-out line, get the **case number** (`ADB-…`) and confirmation that no fee will be charged. Tell the user why: the transcript disappears when the chat closes, but the case number is Adobe's official reference for what was agreed — the user's proof, in Adobe's own system. Give it to the user with the date and the rep's first name (for their own records; the transcript names an identifiable person — keep it private). A fee raised minutes earlier was, in the author's run, *cancelled before settlement* — better than a refund.
9. Verify: one e-mail per plan from `noreply@adobe.com`, subject "Your service will end on <date>", usually within ~2 minutes. If you can't read the mailbox, ask the user to confirm it arrived before you report; don't mark a plan cancelled on the rep's word alone. Access continues until the stated date.

## Step 3 — Self-serve cancel (fallback, or fast path for monthly / 14-day plans)

**Goal: reach Adobe's own review screen that states the fee, the end date, and the card, without accepting any offer on the way.** Path seen in August 2026: `/plans` → **Manage plan** → **End service** → **Cancel plan**, then four screens — fee & end-date summary; reasons (tick one; "No, thanks" on the switch-plan popup); offers ("No, thanks"); review. Adobe may reorder, merge, or add screens; whatever the layout, decline every offer, and treat any button labelled Continue/Confirm/Cancel plan on a screen that shows an amount as the final step (rule 8 + rule 5). **Stop on the review screen and show the user the amount and the end date.** At zero (monthly, or a full refund inside 14 days) ask once — *"Cancel ‹plan› now? It ends on ‹date›, nothing charged. Go ahead?"* — and confirm on their yes. Any other amount: proceed only with their explicit yes to that number; otherwise return to Step 2. Adobe may then auto-open an Adobe Express offer with a countdown: dismiss it (X / "No thanks" / Esc). Do not accept any trial or offer; if it isn't obviously a dismissable upsell, stop and ask.

## Step 4 — Marketing e-mail off (optional, 30 s)

Only if at least one plan was cancelled, ask once: *"Also switch off Adobe's marketing e-mail?"* On yes: `account.adobe.com` → top nav **Communication preferences** → **Offers and insights** → untick **E-mail** (auto-saves). Then **Newsletters**: all toggles Off. Direct URLs like `/profile/communication` 404; use the nav.

## Step 5 — Report

```markdown
| Plan | Status | Access until | Fee outcome | Case number |
|---|---|---|---|---|
| Photography plan (annual, paid monthly) | Cancelled via chat 2026-08-29, rep: A. | 2026-09-05 | ETF waived; nothing charged | ADB-XXXXXXXX-XXXX |
```

Then: Adobe's confirmation e-mail is the official verification; the case number is the user's reference with Adobe from now on.

## When things go wrong

- **Rep won't waive.** Ask once more, politely; then (after the rule-5 gate) ask for *"cancel at end of term, no further charges"* — fee-free per Adobe's published terms and in every case seen so far. Still no: end the chat and try again another day; outcomes seem to vary by rep.
- **Bot keeps looping.** Refresh; then `Talk to a human agent` → Yes → Something else → Billing / Payment, nothing else.
- **A fee was already confirmed on the website today.** Go straight to chat with the refund line from the script; in the author's run a same-day charge was cancelled before settlement.
- **No chat in the region.** Stop and tell the user. The script works verbatim on Adobe's phone support, but the user must make that call.
- **UI doesn't match this file.** Rule 8: stop, describe, ask. After the run, tell the user what differed so they can report it (README → "Keeping it current"); the click paths are the only part of this skill that goes stale.

## What we observed (August 2026, EU individual account, one author)

- ETF = 50% of remaining term, shown live on the self-serve fee screen.
- The 14-day full-refund window applied to new orders; whether plan switches or renewals reset it is unknown — don't rely on it.
- Chat was English-only for the PL locale. Weekend afternoon queue ≈ 5 min.
- The rep made one retention offer first; declining once was enough.
- Verified on: Acrobat Pro and Photography plan, both annual-paid-monthly, individual account, run from Claude Code. Other plan types are handled by the triage rules above, not by a verified run; other agents are format-compatible, not individually verified.

---

Not affiliated with, endorsed by, or sponsored by Adobe. "Adobe", "Acrobat" and "Creative Cloud" are trademarks of Adobe Inc., used only to describe what this procedure does. Automating contact with a company's support channel may conflict with that company's terms of use — that is the user's call. A fee waiver is never guaranteed. Not legal or financial advice.
Licensed under PolyForm Noncommercial 1.0.0 — <https://polyformproject.org/licenses/noncommercial/1.0.0>. Required Notice: Copyright yeahneck (https://github.com/yeahneck)
