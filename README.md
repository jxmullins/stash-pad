# Thought Inbox

A universal LLM skill for capturing and organizing thoughts, ideas, and todos using a simple file-based inbox system.

## What It Does

- **Capture quickly**: Say `todo: your thought here` and it's saved
- **Batch input**: Use semicolons to add multiple items at once
- **Classify later**: Say `classify` to organize everything into categories
- **Works anywhere**: Compatible with Claude, Gemini, Codex, and other LLMs

## Quick Start

### 1. Install the Skill

**For Claude Code:**
```bash
# Copy to your project
cp SKILL.md /your/project/.claude/skills/thought-inbox.md

# Or reference in CLAUDE.md
echo "See .claude/skills/thought-inbox.md for todo management" >> /your/project/CLAUDE.md
```

**For Gemini / Codex / Others:**
Include the contents of `SKILL.md` in your system prompt or instructions file.

### 2. Create a TODO.md

Copy the template to your project:
```bash
cp templates/TODO.md /your/project/TODO.md
```

### 3. Start Capturing

```
You: todo: add user authentication
AI: Added to inbox. (That's a Feature)

You: idea: what if we used websockets; maybe add caching; fix that login bug
AI: Added 3 items to inbox.

You: classify
AI: Classified 4 items:
    Features (2) - auth, websockets
    Improvements (1) - caching
    Bug Fixes (1) - login bug
```

## Usage

| Command | What It Does |
|---------|--------------|
| `todo: <text>` | Add to inbox |
| `idea: <text>` | Add to inbox |
| `todo: a; b; c` | Add multiple items |
| `classify` | Organize inbox into categories |
| `show todos` | Display current list |

## Categories

Default categories (customizable per-project):

- **Features** - New functionality
- **Improvements** - Enhancements to existing code
- **Bug Fixes** - Issues to fix
- **Documentation** - Docs, README, guides
- **Ideas** - Exploratory thoughts

## Customization

Edit your project's `TODO.md` to add custom categories:

```markdown
## Technical Debt
<!-- Code that needs refactoring -->

## Research
<!-- Topics to investigate -->

## Questions
<!-- Things to clarify -->
```

The AI will detect and use your custom categories when classifying.

## Contributing

This skill is being actively developed. Ideas and contributions welcome!

## License

MIT - Use it, share it, modify it.

---

Built with Claude Code.
