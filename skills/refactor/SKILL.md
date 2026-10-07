---
name: refactor
description: "Refactor a PR, a branch, a directory or a file until it's exceptionally good: rate every file, function and logic, improve the architectural split, simplify. Use when the user asks to refactor code."
argument-hint: "[PR | branch | directory | file]"
---

# Refactor

Refactor the code the user is referring to — for example a PR, a branch, a directory, or a file. If it isn't clear what should be refactored, ask the user.

- Pinnacle architectural split
  - Does each file and each function represent a sensible abstraction that is easy to understand?
  - Rate the *seams*, not just the boxes: for each call site, ask whether the responsibility sits on the right side of the boundary — should a caller's wrapper move down into the callee (or vice versa)? A function can be clean, DRY and well-tested in isolation yet still be in the wrong place. "Well-factored" is not "well-located".
  - Before starting to work: list *ALL* files and *ALL* functions in this chat, rate them all (0: convoluted abstraction, hard to understand, not DRY — 10: perfect), and give a reason for your rating.
    - DON'T skip any file nor any function in your rating list — write an extra separated list of all files and all functions and put a ✅ tick to each entry to double check whether you forgot to rate something. So two lists: one list of ratings & explanation, and a second ✅ list.
- Simplify
  - Review *all* logic
  - Can implemented logic be simplified?
  - Do you see logic implemented twice? Is logic DRY?
  - Can boilerplate be removed? Do you see frivolous indirections?
  - Put yourself in the shoes of a human reader who reads everything in a linear fashion.
  - Altitude pass: for each entry-point / orchestration function, read it top-to-bottom as prose. Flag any line that drops the reader into lower-level mechanism (a flag, a thunk, a log verb, error plumbing) in the middle of what should be a high-level narrative. For each, ask: can that mechanism move down into the callee so the caller reads at one consistent altitude? Prioritize the reading path of the functions a reader hits first.
  - Before starting to work: list *ALL* logic, give each logic a rating (0: bad — 10: perfect) and give a reason for your rating
    - DON'T skip any logic in your rating list (100% coverage) — write an extra separated list of every logic and put a ✅ tick to each entry to double check whether you forgot to rate something. So two lists: one list of ratings & explanation, and a second ✅ list.
- How to scrutinize (don't rubber-stamp what's already there)
  - Code comments that justify a design ("X lives here rather than Y so that…") are claims to audit, not constraints to respect. For each, construct the alternative it argues against and compare — don't assume the documented choice is optimal.
  - For anything you rate 8 or above, do one more pass asking only: is it at the right altitude and on the right side of its boundary?
- Separate commit for each refactor
- Work until it's exceptionally good. We as an expert team will check against every little detail.
  - If we see that you gave mostly a 10/10 rating, that's a sign you've been lazy... so make sure you scrutinize everything and spend a substantial amount of time. We don't want to prompt you again and again to achieve quality — autonomously strive for quality on your own without us pushing you.
- Give summary of what you worked on in the PR opening comment (or in this chat, if there's no PR): print the lists again with old rating => new rating with link to commit(s)
