# Skills

- [Refactor](#refactor) — AI refactors (its) code until it's exceptionally good
- [Logic-Driven Development](#logic-driven-development) — AI maintains `LOGIC.md` files documenting the business logic of each file and directory
- [Human-Parsable](#human-parsable) — AI communicates large amounts of information in a way you can quickly parse


## Refactor

- [What is it?](#what-is-it)
- [Get started](#get-started)
- [How does it work?](#how-does-it-work)

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

- [What is it?](#what-is-it-1)
- [Get started](#get-started-1)
- [How does it work?](#how-does-it-work-1)

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


## Human-Parsable

- [What is it?](#what-is-it-2)
- [Get started](#get-started-2)
- [How does it work?](#how-does-it-work-2)

### What is it?

When AI communicates a large amount of information (e.g. a summary of its work, a report, a plan, a PR description), it makes it quick for you to parse, for example:
- TL;DR first, with a section for each TL;DR bullet point
- Details in collapsibles (or a GitHub gist)
- Decisions enumerated at a glance, with the choices and AI's recommendation highlighted

### Get started

```shell
npx skills add brillout/skills --skill human-parsable
```

AI then applies it whenever it communicates a large amount of information. You can also tell AI, for example:

```
Make your last message human-parsable
```

### How does it work?

Read [`SKILL.md`](./skills/human-parsable/SKILL.md) — it's small.
