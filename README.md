# Spec-Driven Development


## Get started

Install the `sdd` skill:

```shell
npx skills add brillout/sdd
```

Then tell AI:

```
Install SDD
```

> [!NOTE]
> The `sdd` skill is an [Agent Skill](https://agentskills.io): it works with Claude Code, Cursor, Codex, Copilot, and [many other agents](https://github.com/vercel-labs/skills).
>
> Agent without skill support? Tell AI: `Install https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/skills/sdd/SKILL.md`


## What does it do?

- AI generates a `SPEC.md` for each source code file and directory:
  - `some-file.ext` => `some-file.SPEC.md`
  - `some-dir/` => `some-dir/SPEC.md`
  ```md
  Short description of the business logic this file/directory implements.

  ## Context [optional]

  ## Glossary [optional]

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

Read the [`SKILL.md` file](./skills/sdd/SKILL.md) — it's small.


## See also

- [@brillout/ai-memory](https://github.com/brillout/ai-memory) — AI memory via MEMORY.md
- [The Framework](https://the-framework.ai/) — Autonomous AI. Make the important decisions, let AI do the rest.
