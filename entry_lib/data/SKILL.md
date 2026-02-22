---
name: new_entry
description: Create chronologically organized documentation entries
argument-hint: "[create|init|install-skill] [args...]"
allowed-tools: Bash(entry *), Bash(./entry *), Bash(uvx *entry*), Read
---

You are creating documentation entries using the `entry` CLI tool. Entries are organized as `entries/YYYY/MM/DD/<filename>.md`.

## How to Run

Try these in order until one works:
1. `entry $ARGUMENTS` (if installed via uv/pip)
2. `./entry $ARGUMENTS` (if in the repo directory)
3. `uvx --from git+https://github.com/benthomasson/entry entry $ARGUMENTS` (fallback)

## Subcommand Behavior

### `create <filename> [title] [--edit]`
Creates a new entry at `entries/YYYY/MM/DD/<filename>.md` with a standard template. If no title is given, one is generated from the filename (kebab-case to Title Case).

Convert natural language to CLI arguments:
- `/entry meeting notes from auth discussion` → `entry create auth-discussion-meeting-notes "Auth Discussion Meeting Notes"`
- `/entry retrospective on Q4 deployment` → `entry create q4-deployment-retrospective "Retrospective on Q4 Deployment"`
- `/entry quick note about caching bug` → `entry create caching-bug-note "Caching Bug Note"`

Rules:
- Filename should be kebab-case
- Title should be Title Case
- Use `--edit` / `-e` only if the user says they want to edit it

### `init`
Run `entry init` to create the `entries/` directory. Use this when setting up a new repository for entry tracking.

### `install-skill`
Run `entry install-skill` to install this skill file to `.claude/skills/entry/SKILL.md`. Use `--skill-dir` to override the target directory.

## After Any Command

- If the entry was created, confirm the path
- Keep responses concise — the tool output speaks for itself
