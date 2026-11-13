---
name: watch
description: Watch a project's public maintainer activity, and post a weekly summary (e.g. GitHub Discussion)
argument-hint: add-project <project> <forum-link> | weekly <thread-url> | update-skill <thread-url>
disable-model-invocation: true
---

## Goal

AI watches for project activity and posts a weekly summary.


## Workflow

Add project:
- Create new thread at `<forum-link>` (e.g. GitHub Discussion)
  - Opening comment example:
    ```md
    # Watch [project-name]

    Settings:
    - [settings]
    - Permalink to [this-skill]

    ## Features

    List of current features (high-level birds view only)

    ## Priority

    List of current priorities (high-level birds view only)
    ```
  - Save all `[settings]` in that opening comment
- Run the weekly workflow once
- Create the "weekly agent" (e.g. prompt `Run weekly workflow of the watch skill linked at [thread-url]`), so that the weekly workflow runs every week

Weekly:
- Read the settings from the thread's opening comment
- Find all the places where public maintainer work happens, for example:
  - Project repository (e.g. GitHub repository)
  - Forums (GitHub Issues, GitHub Discussions, ...)
  - Maintain this list of places at `[settings]`
- Read entire maintainer activity since `Last run` (first run: last 7 days)
- Update `Last run` at `[settings]`
- Update `## Features` and `## Priority` in the opening comment
- Report summary of what happened by adding a comment to the thread
  - For example:
    ```md
    ## March - Week: 2
    - 42 bugs fixed
    - 2 new features:
      - Feature A
      - Feature B
    - New priority: ...
    ```
    The `Week: 2` number doesn't need to be precise

Update skill:
- Replace the `Permalink to [this-skill]` in the thread's opening comment with a permalink to the latest version of this skill


## Requirements

- Thread platform (e.g. GitHub Discussion)
- Being able to create the "weekly agent"

If not met, fail loudly (e.g. `**ERROR**: aborted because ...`).


## Arguments

`$ARGUMENTS` is either:
- `add-project <project> <forum-link>` => run `Add project:`
- `weekly <thread-url>` => run `Weekly:` only
- `update-skill <thread-url>` => run `Update skill:` only
