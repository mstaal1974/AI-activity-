# The Inbox — Email Triage

An interactive e-learning activity for **ABC Training & Consulting · Course 1.9, Lesson 2 —
Phishing & Social Engineering** (prepared for ALS).

## What it teaches

Triage, not paranoia. The learner works through a realistic inbox of six messages and, for
each one, chooses one of three actions:

- **Safe — act on it**
- **Verify first**
- **Report as phishing**

The point is that "report everything" is *not* the right answer. Two of the six messages are
genuinely fine (a firmware notice, an internal IT heads-up), two need a phone-call
verification (a client asking for results at a personal address, a supplier changing bank
details), and two are phishing (a lookalike accreditation portal, a fake document-share
link). Marking a legitimate message as phishing is treated as **over-reporting** and is
corrected with a warm note, never scored as correct.

## The mechanic

**TRIAGE · 6 messages · 3 actions · ~10 min.** Nothing is marked right or wrong until all
six messages have an action and the learner presses **Check my triage**. On check, each
message shows a correct/incorrect verdict in both the list and the reading pane, the
reasoning (`why`) is revealed, a score line appears, and the closing reflection is shown.
Over-reported legitimate messages also surface an amber correction note. A **Start again**
control replays the activity.

## How to open

Just open `index.html` in any modern browser (double-click it). There is no build step, no
install, and no network connection required — everything (HTML, CSS, JavaScript) lives in
the single file and runs offline from `file://`.

## Notes

- All senders, domains, people, and results are **fictional**.
- Before publishing, **ALS should localise the reporting contacts and incident-response
  steps** (e.g. who "Report as phishing" actually routes to, and the internal verification
  channels referenced in the feedback) to match its own environment.
- Australian English throughout. Keyboard-operable, screen-reader friendly (text verdicts
  and `aria-live` feedback), respects reduced-motion, and responsive down to mobile.
