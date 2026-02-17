# Codex Agent Entrypoint

This repository uses a persistent Codex workflow.

Before performing any task:

1. Read `.codex/README.md`
2. Read relevant files in:
   - `.codex/memory/`
   - `.codex/helpers/`
   - `.codex/inbox/`
3. Follow the operating contract strictly

`.codex/README.md` is the single source of truth for:
- workflow rules
- memory usage
- helper scripts
- task procedures

Do not duplicate or override its instructions.
