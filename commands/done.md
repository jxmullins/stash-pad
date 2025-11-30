---
description: Mark a todo item as complete
allowed-tools: [Read, Edit, Write]
argument-hint: "<search text>"
---

Mark the matching item as complete in `TODO.md`.

## Rules
- Search all categories for matching text (partial, case-insensitive)
- Change `- [ ]` to `- [x]`
- Add date prefix: `- [x] YYYY.MM.DD - item text`
- Move the item to the `## Completed` section
- Confirm: "✓ Marked 'item text' complete"

## Handling Ambiguity
If multiple items match the search text, list all matches with numbers and ask the user to specify which one(s) to mark complete.

## File Location
Look for `TODO.md` in the project root. If not found, check for `TODOS.md`, `todo.md`, or `.todo/inbox.md`.
