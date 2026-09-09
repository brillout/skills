# Spec-Driven Development


## Get started

Install the skill:

```bash
mkdir -p .claude/skills/sdd
curl -sL https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md -o .claude/skills/sdd/SKILL.md
```

Then tell AI:

```
Set up spec-driven development
```

> [!NOTE]
> [https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md](https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md) is the raw link of the `sdd.md` file of this repository — it's a skill file, so installing SDD is just downloading it to `.claude/skills/sdd/SKILL.md`. Use `~/.claude/skills/sdd/SKILL.md` instead to install it for all your repositories.

For an AI that doesn't support skills, tell AI:

```
Install https://raw.githubusercontent.com/brillout/sdd/refs/heads/main/sdd.md
```


## What does it do?

- AI generates `.spec.md` for each source code file:
  ```md
  One-sentence description of what this file/directory does.

  ## TLDR

  - Code does this
  - And that
  - ...

  ## Problems

  List of non-obvious problems.

  ## Decisions

  List of non-obvious decisions.

  ## Facts

  List of non-obvious uncommon knowledge.

  ## Flows

  List of all high-level flows.
  ```
- AI will maintain these `.spec.md` files


## Why?

It enables you to:
- When AI makes a change, quickly read the modified business logic instead of reading code
- Quickly navigate unfamiliar code


## How does it work?

Read the [`sdd.md` file](./sdd.md) — it's small.


## See also

- [@brillout/ai-memory](https://github.com/brillout/ai-memory) — AI memory via MEMORY.md
- [The Framework](https://the-framework.ai/) — Autonomous AI. Make the important decisions, let AI do the rest.
