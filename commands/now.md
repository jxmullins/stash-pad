---
description: Add items and classify them immediately
allowed-tools: [Read, Edit, Write]
argument-hint: "<item> [; item2; item3...]"
---

Add item(s) to the inbox and immediately classify them into appropriate categories.

## Rules
- Parse semicolons as delimiters for multiple items
- Add items to the Inbox section first
- Immediately classify all Inbox items (including any pre-existing ones)
- Return a combined confirmation showing what was added and where it was classified

## Example Response
```
Added 2 items and classified:
  Features: "add dark mode"
  Bug Fixes: "fix login timeout"
```

## File Location
Look for `TODO.md` in the project root. If not found, check for `TODOS.md`, `todo.md`, or `.todo/inbox.md`.

If no todo file exists, ask the user before creating one using the template from `${CLAUDE_PLUGIN_ROOT}/templates/TODO.md`.
