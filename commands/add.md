---
description: Add items to your todo inbox (supports semicolon-separated batch entry)
allowed-tools: [Read, Edit, Write]
argument-hint: "<item> [; item2; item3...]"
---

Add the provided item(s) to the `## Inbox` section of `TODO.md`.

## Rules
- Parse semicolons as delimiters for multiple items
- Each item becomes `- [ ] <item>`
- Create Inbox section if missing
- Preserve original wording exactly
- Confirm with count: "Added N item(s) to inbox"

## File Location
Look for `TODO.md` in the project root. If not found, check for `TODOS.md`, `todo.md`, or `.todo/inbox.md`.

If no todo file exists, ask the user before creating one using the template from `${CLAUDE_PLUGIN_ROOT}/templates/TODO.md`.
