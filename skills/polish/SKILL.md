---
name: polish
description: Walk through all user-facing flows, finding and fixing bugs, inconsistencies, UX paper cuts, and UI imperfections.
argument-hint: "[setup] [scope: logic|UX|UI|...]"
---

## Goal

Fix all issues: bugs, inconsistencies, UX paper cuts, UI imperfections, ...

Strive for a highly polished premium result.


## Workflow

Preliminary work:
- Analyze test setup
  - Goal: efficiently find issues
  - Loudly (e.g. `## **Setup quality**: 10/10 ✨` / `0/10 😨`) communicate quality to user
  - Communicate ideas (e.g. `### Setup **suggestions**`) if any
  - If bad: ask e.g. "Proceed despite bad setup?"

Work:
- Thoroughly walk through all user-facing flows, one flow at a time
  - Don't skip anything. Every single flow and any single detail matters.
- Multiple checks (for each flow consider making one thorough pass per check)
  - Inconsistencies? Does everything make sense (from user POV)?
  - Easy for the user to use?
  - UX paper cuts?
  - Bugs?
  - UI imperfections?
  - ...

Communication:
- Show comprehensive list
  - List and enumerate all user-facing flows, for each flow:
    - Either `❓` if not tested, `✅` if no issues found, or `🧹 <number-of-changes>` with list of changes and explanation
    - Show a rating for each flow (0: bad — 10: perfect) with a reason for the rating
    - Two ratings: before/after
    - For UI changes: before/after screenshots/screencasts
- Show overview
  - E.g. `## Overview` with bullet points
  - Loudly (e.g. `### **Changed flows**`) state major changes
  - E.g. `### **Questions**` with your recommendation for each open question
  - Emphasise everything that needs attention


## Arguments

Raw arguments: `$ARGUMENTS`

- Contains `setup` => **setup-only mode**: do only the test-setup part of the preliminary work (analyze, report, suggest)
- Any other words => **scope** (e.g. `logic`, `UX`, `UI`, or a feature/area name). Only fix issues within that scope. Out-of-scope issues you notice: list them, don't fix them.
- Empty => infer the mode/scope from the user's request; if none is given, full run.
