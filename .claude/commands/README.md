# Claude Code Commands for Bodhya

This directory contains slash commands for use in Claude Code sessions. Each `.md` file defines a command that can be invoked with `/command-name`.

## Commands at a Glance

| Command | Purpose | Best For |
|---------|---------|----------|
| `/optimize` | Comprehensive code, UX, and design audit | Before major commits or production pushes |
| `/visual-check` | Screenshots at multiple viewport sizes | After CSS changes or design updates |
| `/build-check` | Verify site builds without errors | Before committing code |
| `/new-content` | Create new pages or blog posts | Adding blog posts or new pages |
| `/seo-check` | Search engine optimization audit | Before publishing content |

## How to Use

In a Claude Code session, type any command like:
```
/optimize
```

Claude will read the corresponding `.md` file and execute the steps defined there.

## Command File Structure

Each command file has:
1. **Title** — The command name
2. **Instructions** — What Claude should do
3. **Steps** — Sequential steps to follow
4. **Use This Command When** — Guidance on when to invoke it

## Adding New Commands

To create a new command:
1. Create a new `.md` file in this directory
2. Name it after the command (e.g., `fix-accessibility.md`)
3. Follow the structure above
4. Reference it in `CLAUDE.md` if it's a commonly-used command

## Command Dependencies

Some commands work well together:
- `/new-content` → `/build-check` → `/visual-check`
- Any change → `/build-check` → `/optimize` (for pre-production review)

Always run `/clear` between unrelated tasks to reset Claude's context.
