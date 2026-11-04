---
name: human-parsable
description: >-
  Efficiently communicating large amounts of information to humans.
  For example: a final summary of your work, a report, a plan, a review, a PR description.
  Before writing such a message, you must always read this skill.
  For a task that will end with such a message, read it when you start the task.
argument-hint: "What should be made human-parsable? Default: the agent's last message."
---

# Human-Parsable

## Goal

Make large amounts of information human-parsable: the human gets the gist in seconds and finds any detail without reading everything.

That's the only rule. Everything below is a toolbox of examples — use what helps, skip what doesn't, be creative.

Small amount of information => just answer, structure is overhead.

## Structure

The human reads top-down and stops once they've had enough => each layer stands on its own:
1. **TL;DR** — a few bullet points, one line each: everything important at a glance
2. **Sections** — one `## Subsection` per TL;DR bullet, same name and same order (skip it if the bullet says it all)
3. **Details** — in collapsibles or a GitHub gist (if available)
   - Collapsibles don't render everywhere (e.g. terminal) => use a gist or a file instead

## Decisions

List and enumerate decisions => the human sees all decisions at a glance:
- Two groups: needs the human's input vs. made by you (=> the human can veto)
- Highlight the choices and your recommendation
- Numbers for decisions, letters for choices => the human can reply `1B`

## Example

```md
## TL;DR

- **Decisions** — 1 needs your input, 1 made by me
- **Login bug** — fixed: expired tokens are now refreshed instead of logging the user out
- **Tests** — ✅ 41 pass, ⚠️ 1 flaky (also fails on `main`)

## Decisions

Needs your input:

1. **Token lifetime?**
   - **A) 1 hour (recommended)** — common default
   - B) 1 day — fewer refreshes, but riskier if leaked

Made by me (veto if you disagree):

2. **Retry once after refreshing** — instead of failing the request

## Login bug

...

## Tests

<details>
<summary>Flaky test log</summary>

...

</details>
```

## More ideas

- What the human must act on comes first
- Results, not the journey — order by importance to the human, not by the order you did things
- Flag surprises, risks and what you didn't verify — never bury them
- Concrete: `3/12 tests fail`, not `some tests fail`
- Bold lead words => the eye scans the left edge
- Tables to compare items across the same attributes
- Before => after, e.g. `timeout: 5s => 30s`
- Show, don't tell: a 3-line snippet beats a paragraph
- Link instead of paste: files, lines, commits, PRs
- No private jargon: names you coined while working mean nothing to the human
- Say it once (besides the TL;DR) — cut what the human wouldn't miss
- Emphasis is a budget: overuse it (bold, emoji) and nothing stands out
- Use what the medium renders, e.g. on GitHub: Mermaid diagrams, alerts (`> [!WARNING]`)

## Before sending

Skim it as the human would: the gist in 10 seconds? Every decision at a glance? If not, restructure.

## When the user invokes this skill

Make human-parsable what the user told you (e.g. message, PR description, or document). By default, your last message.
