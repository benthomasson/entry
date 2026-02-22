# entry

CLI tool for creating chronologically organized documentation entries.

## Install

```bash
# One-shot
uvx --from git+https://github.com/benthomasson/entry entry create my-note

# Permanent
uv tool install git+https://github.com/benthomasson/entry

# Development
git clone https://github.com/benthomasson/entry
cd entry
uv tool install -e .

# pip
pip install git+https://github.com/benthomasson/entry
```

## Usage

```bash
# Create an entry
entry create my-finding "My Finding Title"

# Auto-title from filename (becomes "My Finding")
entry create my-finding

# Create and open in editor
entry create my-finding --edit

# Initialize entries/ directory
entry init

# Install Claude Code skill
entry install-skill
```

## Entry Template

Created entries follow this template:

```markdown
# {Title}

**Date:** YYYY-MM-DD
**Time:** HH:MM

## Overview

## Details

## Next Steps

## Related
```

Entries are placed in `entries/YYYY/MM/DD/<filename>.md`.

## Claude Code Skill

Install the bundled skill so agents can use `/entry` as a slash command:

```bash
entry install-skill
```

This copies the skill to `.claude/skills/entry/SKILL.md`.

## Migration from `new_entry`

If you have a `new_entry` script in your repo, replace it:

```bash
# Install entry globally
uv tool install git+https://github.com/benthomasson/entry

# Remove the old script
rm new_entry

# Same behavior
entry create my-note "My Note"
```
