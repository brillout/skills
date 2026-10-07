# Skills

- [Refactor](#refactor) — AI rates and refactors your code until it's exceptionally good
- [Logic-Driven Development](#logic-driven-development) — AI maintains a `LOGIC.md` documenting the business logic of each file and directory


## Refactor

- [What is it?](#what-is-it) — AI rates and refactors your code, one commit per refactor
- [Get started](#get-started) — install the skill and tell AI what to refactor
- [How does it work?](#how-does-it-work) — read the (small) `SKILL.md`

### What is it?

AI rates every file, function and logic of the code you point it at (a PR, a branch, a directory, ...), then refactors until it's exceptionally good — one commit per refactor, with a summary of old rating => new rating.

### Get started

```shell
npx skills add brillout/skills --skill refactor
```

Then tell AI what to refactor, for example:

```
Refactor this PR
```

### How does it work?

Read [`SKILL.md`](./skills/refactor/SKILL.md) — it's small.


## Logic-Driven Development

- [What is it?](#what-is-it-1) — a `LOGIC.md` for each source file and directory
- [Get started](#get-started-1) — install the skill and tell AI to install LDD
- [How does it work?](#how-does-it-work-1) — read the (small) `SKILL.md`

### What is it?

AI generates and maintains a `LOGIC.md` for each source code file and directory:
- `some-file.ext` => `some-file.LOGIC.md`
- `some-dir/` => `some-dir/LOGIC.md`

```md
Short description of the business logic this file/directory implements.

## Business logic — TL;DR

- **Some business logic** - short description
- **Some other business logic** - short description

## Business logic

### Some business logic

#### Context

#### Business logic

### Some other business logic

...
```

**Why?**

It enables you to:
- When AI makes a change, quickly read the modified business logic instead of reading code
- Quickly navigate unfamiliar code

### Get started

Install the `logic-driven-development` skill:

```shell
npx skills add brillout/skills --skill logic-driven-development
```

Then tell AI:

```
Install LDD
```

### How does it work?

Read [`SKILL.md`](./skills/logic-driven-development/SKILL.md) — it's small.
