---
name: sdd
description: Spec-driven development — every source code file and directory has a `SPEC.md` file next to it describing the business logic it implements, written for a technical product manager who never reads the code. Use this whenever creating, modifying, reviewing or answering questions about `SPEC.md` files, whenever setting up spec-driven development in a repository, and whenever you change source code in a repository that has `SPEC.md` files, since the `SPEC.md` files must be updated together with the code.
---

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

You must always read and respect the `sdd` skill — or, if it isn't installed, https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md
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

1. Install this file as a skill:
   ```bash
   mkdir -p .claude/skills/sdd
   curl -sL https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md -o .claude/skills/sdd/SKILL.md
   ```
   - Replace `.claude/skills/` with `~/.claude/skills/` to install it for all your repositories
   - Skip this step for an AI that doesn't support skills: the `AGENTS.md` line of step 3 is enough
2. Generate a `SPEC.md` file for each file and directory containing software source code
3. Make sure `AGENTS.md` contains: "Before modifying/creating SPEC.md files, you must always read and respect the `sdd` skill — or, if it isn't installed, https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md"
