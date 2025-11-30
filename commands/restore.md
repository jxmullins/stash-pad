---
description: Recover items from the completed list
allowed-tools: [Read, Edit, Write]
argument-hint: "[number or search text]"
---

Restore completed items back to the Inbox.

## Modes

### No argument
Display completed items as a numbered list (newest first) so the user can choose which to restore.

### With number(s)
Restore the specified item(s) by their number in the list.

### With text
Search the Completed section for matching items (partial, case-insensitive) and restore them.

## Rules
- Remove the item from `## Completed`
- Remove the date prefix and completion mark
- Add as `- [ ] <item text>` to the `## Inbox` section
- Confirm: "Restored 'item text' to inbox"

## File Location
Look for `TODO.md` in the project root. If not found, check for `TODOS.md`, `todo.md`, or `.todo/inbox.md`.
