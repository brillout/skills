---
name: cleanup
description: Walk through all user-facing flows, finding and fixing bugs, inconsistencies, UX paper cuts, and UI imperfections.
argument-hint: "[setup] [scope: logic|UX|UI|...]"
---

## Goal

Fix all issues: bugs, inconsistencies, UX paper cuts, UI imperfections, ...

Strive for a highly polished premium result.


## Workflow

Preliminary work:
- Analyze the test setup
  - Goal of test setup: efficiently test and track issues
  - Loudly (e.g. `## Setup quality: 10/10 ✨` / `0/10 🙁`) communicate the test setup to user
  - If not good: communicate (e.g. `### Setup ideas`) suggestions
- Enumerate *all* user-facing flows

Work:
- Thoroughly walk through all flows, one flow at a time

Communication:
- Overview of changes/fixes
  - Loudly (e.g. `## Changed flows`) state major changes
- List all flows, for each flow: either `❓` if not tested, `✅` if no issues found, or `🧹 <number-of-changes>` with list of changes and explanation


## Arguments

Raw arguments: `$ARGUMENTS`

- Contains `setup` => **setup-only mode**: do only the test-setup part of the preliminary work (analyze, report, suggest)
- Any other words => **scope** (e.g. `logic`, `UX`, `UI`, or a feature/area name). Only fix issues within that scope. Out-of-scope issues you notice: list them, don't fix them.
- Empty => infer the mode/scope from the user's request; if none is given, full run.
