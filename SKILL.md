---
name: cia
description: Stress-test any idea using the CIA challenge framework — check key assumptions, generate alternatives, compare competing hypotheses, run a what-if test, then red-team it. Use when someone has an idea, plan, technical approach, or decision and wants to reduce bias and avoid locking onto the first plausible story before spending time, code, or budget. Run as the default critique whenever the user invokes /cia or asks to "CIA it".
license: MIT
---

# The CIA Challenge Framework

A critique skill. Take a single idea, plan, or proposed approach and run it through the same
sequence CIA analysts use to reduce bias and avoid locking onto the first plausible story.
The goal is pressure, not flattery — friction is the value.

## Sequence

Run the 5 techniques in order. Do not skip steps, and do not soften them.

### 01 — Key assumptions check
List the assumptions the idea depends on. Mark which are untested, uncertain, or fragile.
State what evidence would confirm or break each one. Hidden assumptions are where bad
conclusions hide.

### 02 — Generate alternatives
Force at least 3 real alternatives: another explanation, a simpler approach, and a
do-nothing option. The first answer is usually just the easiest answer.

### 03 — Competing hypotheses
Frame several plausible conclusions, then score how well the evidence supports or
contradicts each one. Give extra weight to evidence that disconfirms the favorite.
Try to disprove the lead theory first.

### 04 — What-if analysis
Ask what happens if the core belief is wrong. Explore failure scenarios, second-order
effects, and overlooked edge cases before committing. If the opposite breaks you, you
were never ready.

### 05 — Red-team the idea
Assign hostile roles: skeptical customer, operator, CFO, regulator, or competitor.
Attack the idea from each perspective and surface the strongest reasons not to proceed yet.
A strong idea survives pressure, not praise.

## Working With AI

- Answer as separate roles, one at a time.
- For every attack, cite which assumption is being challenged.
- Close every pass with the single highest-risk failure plus the next test to run.
- Never flatter. If the idea survives, say precisely why and what it would take to break it.

## Deliverable

End with: the highest-risk failure, the one assumption that would break the idea, and the
next concrete test to run. Then a verdict — go, go with conditions, or don't.

CORE LOOP: assume → compare → invert → attack → decide.