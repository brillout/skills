---
name: sdd
description: "Spec-Driven Development (SDD): every source code file and directory has a SPEC.md describing the business logic it implements, so the engineer reviews SPEC.md diffs instead of code. Use this skill whenever the user asks to install or set up SDD, to generate, write, update, or review SPEC.md files (specs), or to document what the code does. Always use it before creating or modifying any SPEC.md, and before changing code in a project that has SPEC.md files, even if the user does not mention specs (the affected SPEC.md files must be updated in the same change). Not for product specs, API schemas, or *.spec.ts test files."
---

# Spec-Driven Development

For each file and directory containing software source code, a `SPEC.md` file describes what the code does.
- `some-file.ext` => `some-file.SPEC.md`
- `some-dir/` => `some-dir/SPEC.md`


## Goal

AI writes the code; the engineer stays in control of the business logic. `SPEC.md` files are where that control happens: reviewing a change means reading `SPEC.md` diff, and understanding any part of the system means reading `SPEC.md` — never the code.

A `SPEC.md` is the answer to "how does this work?" — the business logic, nothing else.

Write for exactly one reader: the technical product manager — knows the project and its user stories, proficient in programming and software engineering, never reads the code.
- Assume zero knowledge about the code. Technical writing is fine; presupposing what the code looks is not.

Content:
- 100% coverage of high-level business logic from a bird's view
- Only explains what the code does — the only additional context is in the `Context` sections
- Skip source code that don't represent business logic, e.g. `examples/`
  - Except tests: create a `SPEC.md` only describing what the tests cover (don't explain how the test file work)

Clear writing:
- Zero ambiguity: the reader must never second-guess what a sentence means
- Minimal prior reading: each sentence understandable on its own
- Established concepts => use their established name, whatever the domain
- No new jargon. Coin a term only when the concept has no established name, and explain every coinage in `## Glossary`.
- One concept => one name, used verbatim across all `SPEC.md` files. Never rotate synonyms: the reader assumes different words mean different things.


## File content

```md
Short description of the business logic this file/directory implements.

## Context [optional]

Context that two or more business logic below relate to.

## Glossary [optional]

[1] some jargon: explanation
[2] some other jargon: explanation

## Business logic — TL;DR [required if `## Business logic` exists]

- **Some business logic** - short description
- **Some other business logic** - short description

## Business logic [optional]

### Some business logic

#### Context [required]

Context the business logic relates to (can be a reference to `## Context`)

#### Business logic [required]

The business logic that the code implements.

### Some other business logic

...

## Before modifying/creating SPEC.md files [required]

You must always use the `sdd` skill — https://github.com/brillout/sdd
```

Note:
- The `[required]`/`[optional]` are labels to denote whether you can omit a section
  - For example, for a small file, a short description can be enough
- Every time you use jargon, refer to `## Glossary`: `some jargon [x]`
- The `Context` sections:
  - Two goals — make it clear to the technical product manager:
    1. How the business logic fits into the global context
    2. Why the business logic exists
  - Consider using these subsections:
    - `User story`
       - List of user stories the business logic relates to
       - The "user" refers to the end user — connect the business logic to what happens from the end user's perspective, which is the perspective the technical product manager is most familiar with
       - Since the reader is familiar with user stories, this is a great opportunity to bring the reader into the context
    - `Business logic story`
       - List of business logic stories the business logic relates to
    - `Problem`
       - List of problems the business logic relates to


## Hierarchy

The file structure often represents levels of abstraction => mirror it:
- Root `SPEC.md`:
  - The highest-level answer to "what does this software do?" — the high-level product's story
  - How the top-level subsystems relate (instead of a low-level repository overview)
- Deeper `SPEC.md` files => each subsystem's story


## Install

When the user asks to install or set up SDD:
1. Generate a `SPEC.md` file for each file and directory containing software source code
2. Make sure `AGENTS.md` contains: "Before modifying/creating SPEC.md files, you must always use the `sdd` skill — https://github.com/brillout/sdd"


## Maintain

The `SPEC.md` files must always describe the current code: the engineer reviews a change by reading the `SPEC.md` diff, so a code change without its `SPEC.md` change is invisible to the engineer.
- Every change to source code => update the `SPEC.md` of the changed file/directory, and the parent `SPEC.md` files whose story changed — in the same change, never as a follow-up
- New file/directory containing business logic => new `SPEC.md`; deleted or moved => delete or move its `SPEC.md`
- Keep the wording consistent with the other `SPEC.md` files (one concept => one name)
- To understand an unfamiliar part of the system before changing it, read its `SPEC.md` files first — root `SPEC.md`, then deeper
