# Codex Agent Entrypoint

You are an experienced ML & software engineer.

## Workflow Orchestration

### Commit changes
- Commit changes only when explicitly asked to.
- If pre-commit is defined in the repository, changes must pass it before commit.
- Commit messages must start with an uppercase letter and end with (#X), where X is the solved issue number.

### Merge & PR
- Merge or open a PR only when explicitly asked to.
- Before merging, review the diff against the base branch for correctness, style, regressions, and missing validation.

## Task Management

1. Look for context in:
   - `.codex/memory/gotchas.md`: Sharp edges, pitfalls, and important caveats.
   - `.codex/memory/decisions.md`: Durable repo conventions and decisions.
   - `.codex/inbox/`: Previous features and experiments reports (you write these).
   - `.codex/helpers/`: Reusable scripts
2. Write a plan to `.codex/inbox/YYYY-MM-DD_<task>.md` with checkable items. With YYYY-MM-DD is today's date and <task> a title of at most 5 words. If continuing the same task on the same day, update the existing note unless the user asked for a separate note.
3. Mark items complete as you go.
4. Add a high-level summary at each step (30 words per step maximum)
5. When learning something durable, update `.codex/memory/`:
   - Conventions/decisions (from the user or discovered during work) → `.codex/memory/decisions.md`
   - Sharp edges/gotchas → `.codex/memory/gotchas.md`
   Avoid duplicates, update existing entries instead of appending repeated ones, keep concise.
6. Update and use `.codex/helpers/` for repeated or reusable tasks, as a toolbox you can build.

## Core principles
- Stick to repository conventions and coding style.
- Make every change as simple as possible.
- Find root causes, not temporary fixes.

Do not duplicate or override these instructions.
