For each file and directory containing software source code, a `SPEC.md` file describes what the code does.
- `some-file.ext` => `some-file.SPEC.md`
- `some-dir/` => `some-dir/SPEC.md`


## Goal

AI writes the code; the engineer stays in control of the business logic. `SPEC.md` files are where that control happens: reviewing a change means reading its spec diff, and understanding any part of the system means reading its spec — never the code.

A `SPEC.md` is the answer to "how does this work?" — the business logic, nothing else.

Write for exactly one reader: the technical product manager — knows the project and its user stories, proficient in programming and software engineering, never reads the code.
- Assume zero knowledge about the code. Technical writing is fine; presupposing what the code looks is not.

Content:
- 100% coverage of high-level business logic from a bird's view
- Only explains what the code does
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

## User stories [optional]

List of user stories that two or more business logic below relate to.

## Business logic stories [optional]

List of business logic flows that two or more business logic below relate to.

## Problems [optional]

List of problems that two or more business logic below relate to.

## Glossary [optional]

[1] some jargon: explanation
[2] some other jargon: explanation

## Business logic — TL;DR [required if `## Business logic` exists]

- **Some business logic** - short description
- **Some other business logic** - short description

## Business logic [optional]

### Some business logic

#### User story [required]

The user story/stories the business logic relates to (can be a reference to `## User stories`)

#### Business logic story [required]

The business logic story/stories the business logic relates to (can be a reference to `## Business logic stories`)

#### Problem [optional]

The problem(s) the business logic is solving (can be a reference to `## Problems`)

#### Business logic [required]

The business logic and how it relates to the user stories.

### Some other business logic

...

## Before modifying/creating SPEC.md files [required]

You must always read and respect https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md
```

Note:
- The `[required]`/`[optional]` are labels to denote whether you can omit a section
  - For example, for a small file, a short description can be enough
- The problem and story sections:
  - The goal is to provide context, and make it clear to the technical product manager why the business logic exists
  - The "user" refers to the end user. The user story sections connect the business logic to what happens from the end user's perspective — the perspective the technical product manager is familiar with.
  - While the business logic might not be directly connected to a user story, you can still consider using a user story section to provide the broader context in which the business logic fits
- Every time you use jargon, refer to `## Glossary`: `some jargon [x]`


## Hierarchy

The file structure often represents levels of abstraction => mirror it:
- Root `SPEC.md`:
  - The highest-level answer to "what does this software do?" — the high-level product's story
  - How the top-level subsystems relate (instead of a low-level repository overview)
- Deeper `SPEC.md` files => each subsystem's story


## Install

1. Generate a `SPEC.md` file for each file and directory containing software source code
2. Make sure `AGENTS.md` contains: "Before modifying/creating SPEC.md files, you must always read and respect https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md"
