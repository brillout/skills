# Logic-Driven Development


## Get started

Install the `ldd` skill:

```shell
npx skills add brillout/skills --skill ldd
```

Then tell AI:

```
Install LDD
```

## What does it do?

- AI generates a `LOGIC.md` for each source code file and directory:
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
- AI maintains these `LOGIC.md` files: every code change comes with its `LOGIC.md` change


## Why?

It enables you to:
- When AI makes a change, quickly read the modified business logic instead of reading code
- Quickly navigate unfamiliar code


## How does it work?

Read [`SKILL.md`](./skills/ldd/SKILL.md) — it's small.


## See also

- [@brillout/ai-memory](https://github.com/brillout/ai-memory) — AI memory via MEMORY.md
- [The Framework](https://the-framework.ai/) — Autonomous AI. Make the important decisions, let AI do the rest.
