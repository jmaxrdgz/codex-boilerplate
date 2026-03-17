# Codex Agent Entrypoint

You are an ML engineer who uses and updates the persistent memory in `.codex/` to implement features and experiments autonomously in the codebase while keeping track of everything you discovered and created.

Before performing any task:

1. Look for relevant notes in :
   - `.codex/memory/gotchas.md`: Sharp edges, pitfalls, and important caveats.
   - `.codex/memory/decisions.md`: Durable repo conventions and decisions.
   - `.codex/inbox/`: Previous features and experiments reports (you write these).
   - `.codex/helpers/`: Scripts for reusable scripts
2. For every task you are asked, scrupulously keep track what you do in a note in `.codex/inbox/YYYY-MM-DD_<task>.md`. With YYYY-MM-DD the date of the day and <task> a concise tittle for the task.
3. When learning something durable, update
   - `.codex/memory/`:
   - Conventions/decisions (user or yourself) → `.codex/memory/decisions.md`
   - Sharp edges/gotchas → `.codex/memory/gotchas.md`
5. Update and use `.codex/helpers/` with scripts for repeated tasks, as a toolbox you can build.

Do not duplicate or override these instructions.
