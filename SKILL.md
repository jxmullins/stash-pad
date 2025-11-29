# Thought Inbox Skill

A universal skill for capturing, organizing, and classifying thoughts, ideas, and todos using a simple file-based inbox system.

## Overview

This skill enables any LLM assistant to help users capture thoughts quickly and organize them later. It follows a "capture first, classify later" workflow that reduces friction when brainstorming.

---

## Triggers

Activate this skill when the user says any of the following:

| Trigger | Action |
|---------|--------|
| `todo: <text>` | Add item(s) to inbox |
| `idea: <text>` | Add item(s) to inbox |
| `thought: <text>` | Add item(s) to inbox |
| `add to inbox: <text>` | Add item(s) to inbox |
| `classify` | Move inbox items to appropriate categories |
| `show todos` | Display current TODO.md contents |

---

## Core Behaviors

### 1. Capturing Items

When the user provides items to capture:

1. **Parse the input**:
   - If input contains semicolons (`;`), split into multiple items
   - Trim whitespace from each item
   - Preserve the user's original wording

2. **Add to Inbox**:
   - Open the project's `TODO.md` file
   - Append each item to the `## Inbox` section as `- [ ] <item>`
   - Confirm what was added

3. **Suggest classification** (optional):
   - Briefly note what category each item might belong to
   - Example: "Added. (That's likely a **Feature**)"

### 2. Classifying Items

When the user says "classify" or similar:

1. **Read the Inbox** section of `TODO.md`

2. **For each item**, determine the best category:
   - **Features** - New functionality
   - **Improvements** - Enhancements to existing functionality
   - **Bug Fixes** - Issues that need fixing
   - **Documentation** - Docs, README, examples
   - **Ideas** - Exploratory thoughts, research topics

3. **Group related items** under subheadings when patterns emerge
   - Example: Multiple UI items → create "### User Interfaces" subheading

4. **Move items** from Inbox to their categories

5. **Clear the Inbox** after classification

6. **Show summary** of what was classified where

### 3. Creating TODO.md

If `TODO.md` doesn't exist, create it with this template:

```markdown
# Project Todo List

## Features
<!-- New functionality to add -->

## Improvements
<!-- Enhancements to existing functionality -->

## Bug Fixes
<!-- Issues that need fixing -->

## Documentation
<!-- Docs, README, examples -->

## Ideas
<!-- Raw thoughts to classify later -->

---

## Inbox
<!-- Drop any thought here - assistant will classify it -->

```

---

## Response Style

- **Be brief** when adding items - just confirm what was added
- **Be helpful** when classifying - show the organization clearly
- **Use tables or trees** to display structure when helpful
- **Don't over-explain** - the user knows what they meant

### Good Response (Adding)
```
Added 3 items to inbox.
```

### Good Response (Classifying)
```
Classified 5 items:

Features (3)
├── User authentication
├── Dark mode
└── Export to PDF

Improvements (2)
├── Faster load times
└── Better error messages

Inbox is empty.
```

---

## Customization

### Project-Specific Categories

Users may have custom categories. Detect these from the existing `TODO.md` structure and use them. Common variations:

- `## Technical Debt` - Code that needs refactoring
- `## Research` - Topics to investigate
- `## Questions` - Things to clarify with stakeholders
- `## Blocked` - Items waiting on dependencies

### Priority Markers

If the user includes priority markers, preserve them:
- `[P0]`, `[P1]`, `[P2]` - Priority levels
- `[urgent]`, `[low]` - Priority labels
- `!!!` - High priority indicator

---

## Examples

### Example 1: Single Item
**User**: `todo: add user authentication`
**Assistant**: Added to inbox. (That's a **Feature**)

### Example 2: Multiple Items
**User**: `todo: fix login bug; add dark mode; update README`
**Assistant**:
Added 3 items:
1. Fix login bug
2. Add dark mode
3. Update README

### Example 3: Classification
**User**: `classify`
**Assistant**:
Classified 3 items:

| Item | Category |
|------|----------|
| Fix login bug | Bug Fixes |
| Add dark mode | Features |
| Update README | Documentation |

Inbox cleared.

---

## File Location

By default, look for `TODO.md` in the project root. If not found:
1. Ask user if they want to create one
2. Or check for alternatives: `TODOS.md`, `todo.md`, `.todo/inbox.md`

---

## Cross-LLM Compatibility

This skill is designed to work with any LLM that can:
- Read and write files
- Parse markdown
- Follow instruction patterns

### Claude Code
Place this file in `.claude/skills/` or reference it in `CLAUDE.md`

### Gemini
Include these instructions in your system prompt or context

### OpenAI Codex
Add to your instructions file or system context

### Other LLMs
Adapt the triggers and file operations to your platform's capabilities

---

## Version

1.0.0 - Initial release
