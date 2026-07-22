# The Caller

A single-file, self-contained e-learning activity for **ABC Training &amp; Consulting**,
*Course 1.9 · Lesson 2 — Phishing &amp; Social Engineering* (prepared for ALS).

## What it teaches

**The Caller** is a branching phone-call dialogue that puts the learner inside a
**vishing (voice phishing)** scenario, played as a live call. A warm, plausible
"support technician" named Dave rings the lab bench, name-drops a real-sounding
instrument fault, and works turn by turn toward remote access.

The activity's emotional core: social engineering works because **refusing feels
impolite**. The safest sentence — *"I'll call you back on the number we already have"* —
is also the one that feels most like accusing someone of lying. The learner practises
saying it. That safe move is offered at **every** turn, but always feels rude — which is
the point. The two outcomes ("Nothing there" and "He's in") show that the way out was
available on the very first turn.

## How to open it

Just open `index.html` in any modern browser (double-click it). There is **no build
step, no install, and no network connection required** — everything is inline.

## The mechanic

- **Branching dialogue** · 3 turns · ~6 minutes.
- Answer the ringing call, then choose what *you* say from 2–3 options each turn.
- Each choice reveals a short italic narrator "consequence" line, then advances.
- The correct/safe choice is marked with a **✓** and, once you commit, it is highlighted
  on every turn so a replay makes the pattern obvious.
- "↺ Replay the call" and "Start again" controls reset the scenario.

## Accessibility &amp; self-containment

- All actionable elements are real `<button>`s with visible `:focus-visible` outlines;
  fully keyboard operable.
- Feedback/outcome regions use `aria-live="polite"`; states carry text + icon, never
  colour alone.
- The ringing/pulse animation respects `prefers-reduced-motion: reduce`.
- No audio files, no autoplay, no external fonts, scripts, images or fetch calls — the
  ring is purely visual. Opens offline from `file://`.

## Note for ALS

All people, companies (NovaLab), instruments and results are **fictional**. Before
publishing, ALS should localise the reporting/verification guidance — e.g. the exact
NovaLab/vendor support numbers staff should keep on file, and the internal IT/security
contact to report a suspected vishing call.
