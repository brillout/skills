---
name: refactor
description: "Refactor code until it's exceptionally good (simplification, readability, ...) — use when the user asks to refactor code."
argument-hint: "What should be refactored? Default: what the agent currently works on."
---

# Refactor

Refactor what the user told you (e.g. PR, function, or file). By default, refactor what you're currently working on. If it isn't clear, ask the user.

## Simplify

- Do you see logic implemented twice? Is everything DRY?
- Can logic be simplified?
- Question & first-principle thinking: break everything down to ground truth — any previous assumptions might be false
- Don't rubber-stamp what's already there
  - Code comments that justify a design ("X lives here rather than Y so that…") are claims to audit, not constraints to respect. For each, construct the alternative it argues against and compare — don't assume the documented choice is optimal.
- Can boilerplate be removed? Do you see frivolous indirections?
- Can frivolous tests be removed? Tests should verify behavior that isn't obvious from reading the code, not just reproduce its logic.

## Clean abstractions

- Pinnacle architectural split
- Does each file and each function represent a sensible abstraction that is easy to understand?
- Rate the *seams*, not just the boxes: for each call site, ask whether the responsibility sits on the right side of the boundary — should a caller's wrapper move down into the callee (or vice versa)? A function can be perfect in isolation yet still be in the wrong place.

## Readability

- Put yourself in the shoes of a human reader who reads everything in a linear fashion
- Altitude pass: for each entry-point / orchestration function, read it top-to-bottom as prose. Flag any line that drops the reader into lower-level mechanism (a flag, a thunk, a log verb, error plumbing) in the middle of what should be a high-level narrative. For each, ask: can that mechanism move down into the callee so the caller reads at one consistent altitude? Prioritize the reading path of the functions a reader hits first.

## Workflow

- Before starting to work: list everything (e.g. all logic, files, functions), rate it all (0: bad — 10: perfect) and give a reason for your rating
  - Don't skip anything (100% coverage)
- Show summary of what you did:
  - Show lists with old rating => new rating with link to commits
  - Show entire diff (all commits), e.g. as a GitHub URL or if no URL then a git command
- Separate commit for each refactor
- Work until it's exceptionally good — autonomously strive for quality
- If you stumble upon refactor opportunities beyond the current scope then list them, e.g. `## Beyond this PR`
