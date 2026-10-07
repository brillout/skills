# Logic-Driven Development (LDD)

## What is LDD?

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


## Get started

Install the `logic-driven-development` skill:

```shell
npx skills add brillout/skills --skill logic-driven-development
```

Then tell AI:

```
Install LDD
```


## How does it work?

Read [`SKILL.md`](./skills/logic-driven-development/SKILL.md) — it's small.


## Other skills

### Refactor

AI rates every file, function and logic of the code you point it at (a PR, a branch, a directory, ...), then refactors until it's exceptionally good — one commit per refactor, with a summary of old rating => new rating.

```shell
npx skills add brillout/skills --skill refactor
```

Then tell AI what to refactor, for example:

```
Refactor this PR
```

Read [`SKILL.md`](./skills/refactor/SKILL.md) — it's small.


## See also

- [@brillout/ai-memory](https://github.com/brillout/ai-memory) — AI memory via MEMORY.md
- [The Framework](https://the-framework.ai/) — Autonomous AI. Make the important decisions, let AI do the rest.
