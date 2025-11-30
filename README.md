# Stash Pad

**Capture todos and ideas without breaking your flow.**

A Claude Code skill for quick task management during coding sessions. Type `:a fix the bug` and keep working—organize later.

[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill%20%7C%20plugin-blue)](https://claude.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-3.0.0-orange)](SKILL.md)

---

## The Problem

You're deep in a coding session. An idea hits. A bug surfaces. A todo pops into your head.

**Old way:** Switch context, open a notes app, lose your train of thought.

**Stash Pad:** Type `:a your thought` and keep coding. Classify everything later with `:c`.

---

## Quick Demo

```
You: :a add user authentication
Claude: Added to inbox.

You: :add websockets; caching; fix login bug
Claude: Added 3 items to inbox.

You: :c
Claude: Classified 4 items:
    Features (2) - auth, websockets
    Improvements (1) - caching
    Bug Fixes (1) - login bug

You: :d auth
Claude: ✓ Marked "add user authentication" complete
```

---

## Install

### Option 1: As Plugin (Recommended)

Full features with slash commands + colon shortcuts:

```bash
/plugin marketplace add https://github.com/jxmullins/stash-pad
/plugin install stash-pad
```

### Option 2: As Skill (Lightweight)

Colon shortcuts only — just copy one file:

```bash
cp SKILL.md /your/project/.claude/skills/stash-pad.md
```

---

## Commands

| Action | Slash Command | Shortcut |
|--------|---------------|----------|
| Add to inbox | `/stash:add` | `:a` |
| Mark complete | `/stash:done` | `:d` |
| Organize inbox | `/stash:classify` | `:c` |
| Display list | `/stash:show` | `:s` |
| Add + classify | `/stash:now` | `:n` |
| Restore item | `/stash:restore` | `:r` |
| Search todos | `/stash:find` | `:f` |
| Clear completed | `/stash:archive` | `:ar` |

*Slash commands available with plugin install. Shortcuts work with both.*

**Batch add:** Use semicolons — `:a fix bug; dark mode; update docs`

---

## Features

- **Zero friction** — Two keystrokes to capture (`:a`)
- **Batch input** — Add multiple items with semicolons
- **Smart classification** — AI sorts into Features, Bugs, Improvements, etc.
- **Restore mistakes** — Accidentally completed? Bring it back with `:r`
- **Search everything** — Find items across all categories
- **Project-local** — Each project gets its own `TODO.md`

---

## Categories

Default categories (auto-detected, customizable):

- **Features** — New functionality
- **Improvements** — Enhancements to existing code
- **Bug Fixes** — Issues to fix
- **Documentation** — Docs, README, guides
- **Ideas** — Exploratory thoughts

Add your own by editing `TODO.md`:

```markdown
## Technical Debt
## Research
## Questions
```

---

## Git

Commit `TODO.md` to track backlog history, or add to `.gitignore` for local-only.

---

## Roadmap

- [x] Core todo management (`:add`, `:done`, `:classify`)
- [x] Search and restore functionality
- [x] Batch entry support
- [x] **Plugin version** — Slash commands (`/stash:add`), tab completion, marketplace distribution
- [ ] MCP integration — Sync with external tools (planned)

---

## Why I Built This

> I can't in good conscience call myself a "vibe coder" because while I can read code and follow along I can't actively write code, so I don't think the 'coder' part is fitting. While working on another project I needed to capture ideas and I didn't really like the other options I had at the moment (Notes.app, TextEdit, etc...) but with my ADHD mind I knew I needed something fast and PRESENT. Working with Claude Code CLI, I quickly created ver. 1.0 in the middle of the other project. It's not fancy but it works for me and I hope someone else can use it too.

---

## Support

If this skill saves you time, consider buying me a coffee:

[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-support-yellow?logo=buy-me-a-coffee)](https://buymeacoffee.com/jxmullins)

## Contributing

Ideas and contributions welcome! This skill is actively developed.

## License

MIT — Use it, share it, modify it.

---

*Built with Claude Code.*
