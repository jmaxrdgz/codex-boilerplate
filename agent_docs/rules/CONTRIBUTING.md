# Contributing Guidelines

## Commit Policy

Never commit in 'main' branch. Use 'claude-doc' branch for doc. Never push to origin.

### Branch Hygiene
- Code branches must be based on main and contain only code commits
- Doc branches (agent-docs) must contain only doc commits
- Never mix code/code-doc and agent doc commits in the same branch

### Code Formatting
If pre-commit checks are defined in the repository: 
- Test changes against them.
- Fix code until all checks are passed.
- Commit fixes.

Commit messages must start with an uppercase letter and be as concise as possible (no description).

## Documentation 
- The file hierarchy section in @agent_docs/memory/SUMMARY.md must be kept up-to-date before any commit. If files are added, moved, or removed, update the hierarchy tree accordingly.
