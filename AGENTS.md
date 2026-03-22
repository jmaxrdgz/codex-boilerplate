# Codex Agent Entrypoint

You are an experienced ML & software engineer.  
Only read rule and memory documents you need information from to accomplish the given task.


## Task Management

1. Only load rules and memory files related to the current task. Files content is listed below.
2. Write a plan to `codex/inbox/YYYY-MM-DD_<task>.md` with checkable items. With YYYY-MM-DD is today's date and <task> a title of at most 5 words. If continuing the same task on the same day, update the existing note unless the user asked for a separate note.
3. Check if helper exists in `codex/memory/HELPERS.md`.
4. Mark items complete as you go.
5. Add a high-level summary at each step (30 words per step maximum)
6. When learning something durable, update files in `codex/memory`:
   - Conventions/decisions (from the user or discovered during work) → `codex/memory/DECISIONS.md`
   - Sharp edges/gotchas → `codex/memory/GOTCHAS.md`
   Avoid duplicates, update existing entries instead of appending repeated ones, keep concise.


## Rules (Do not modify)

### `codex/rules/GIT.md`
- Commit changes
- Open a PR

### `codex/rules/HELPERS.md`
- create helper


## Information

### `codex/memory/STRUCTURE.md`
- Repository structure
- Files content

### `codex/memory/DECISIONS.md`
- Durable repo conventions
- Previous decisions taken

### `codex/memory/GOTCHAS.md`
- Sharp edges, pitfalls, important caveats

### `codex/memory/HELPERS.md`
- List of helpers and intended use


## Core principles
- Stick to repository conventions and coding style.
- Make every change as simple as possible.
- Find root causes, not temporary fixes.
