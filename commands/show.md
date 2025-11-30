---
description: Display your current todo list
allowed-tools: [Read]
---

Display the contents of `TODO.md` in a readable format.

## Rules
- Read and display the full TODO.md file
- Use formatting (tables, trees, or sections) to make it easy to scan
- Show item counts per section
- Highlight any items in the Inbox that need classification

## File Location
Look for `TODO.md` in the project root. If not found, check for `TODOS.md`, `todo.md`, or `.todo/inbox.md`.

If no todo file exists, inform the user and suggest creating one with `/stash:add`.
