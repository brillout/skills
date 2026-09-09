# Spec-Driven Development


## Get started

Install the `sdd` skill:

```shell
npx skills add brillout/skills --skill sdd
```

Then tell AI:

```
Install SDD
```

## What does it do?

- AI generates a `SPEC.md` for each source code file and directory:
  - `some-file.ext` => `some-file.SPEC.md`
  - `some-dir/` => `some-dir/SPEC.md`
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
- AI maintains these `SPEC.md` files: every code change comes with its `SPEC.md` change


## Why?

It enables you to:
- When AI makes a change, quickly read the modified business logic instead of reading code
- Quickly navigate unfamiliar code


## How does it work?

Read [`SKILL.md`](./skills/sdd/SKILL.md) — it's small.


## See also

- [@brillout/ai-memory](https://github.com/brillout/ai-memory) — AI memory via MEMORY.md
- [The Framework](https://the-framework.ai/) — Autonomous AI. Make the important decisions, let AI do the rest.
