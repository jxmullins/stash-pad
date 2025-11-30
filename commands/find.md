---
description: Search all todo sections for matching items
allowed-tools: [Read]
argument-hint: "<search text>"
---

Search across all sections of `TODO.md` for items matching the search text.

## Rules
- Case-insensitive partial matching
- Search all sections (Inbox, Features, Bug Fixes, Completed, etc.)
- Return results grouped by section
- Show "No matches found" if nothing matches

## Example Response
```
Found 3 matches for "auth":

Features:
  - [ ] add user authentication

Bug Fixes:
  - [ ] fix auth token expiry

Completed:
  - [x] 2024.11.15 - setup auth middleware
```

## File Location
Look for `TODO.md` in the project root. If not found, check for `TODOS.md`, `todo.md`, or `.todo/inbox.md`.
