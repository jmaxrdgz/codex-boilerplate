# Codex Operating Contract (repo-local)

## Non-negotiables
0) At the start of any task, read relevant files in:
   - .codex/memory/
   - .codex/helpers/
   - .codex/inbox/
   to reuse existing knowledge instead of rediscovering it.
1) Keep a running task log in `.codex/inbox/YYYY-MM-DD_<task>.md`.
   Create the inbox task file if it does not exist when starting a task.
2) When you learn something durable, update memory:
   - Conventions/decisions → `.codex/memory/decisions.md`
   - Sharp edges/gotchas → `.codex/memory/gotchas.md`
3) Prefer using `.codex/helpers/*` scripts instead of guessing commands.
4) Before finalizing work:
   - run the relevant checks (via helpers)
   - update notes
   - commit code + notes in the same PR/branch
5) End-of-task is not complete until both are done:
   - update memory files when applicable (`.codex/memory/decisions.md`, `.codex/memory/gotchas.md`)
   - commit code changes and `.codex/` note/memory updates together
6) Before you finish, paste the completed checklist from `.codex/templates/task_close.md` into the active inbox task file.
7) For risky changes, require a Reviewer pass before merge.
   - Risky changes include: auth/permissions, migrations, infra/deploy, and anything user-facing or hard to rollback.
   - Workflow:
     - Builder agent does the work and commits.
     - Reviewer agent gets only:
       - the diff (`git diff main...HEAD`)
       - the task goal
     - Reviewer agent is instructed to be adversarial and can return `APPROVE` or `REQUEST_CHANGES`.
8) If a command or workflow is used more than once, create or update a helper script in `.codex/helpers/`.

## Output format for each task
- Plan (short)
- Changes made (files)
- Commands executed + results
- Risks / assumptions
- What was added to memory

## Git hygiene
- Work on a dedicated branch.
- Use small commits if needed, but always include the note updates.
- Never push secrets. Never commit credentials.
