# Git Rules

## Commit
If pre-commit checks are defined in the repository: 
- Test changes against them.
- Fix code until all checks are passed.
- Commit fixes.

Commit messages must start with an uppercase letter and be as concise as possible (no description).

## PR
Only follow if PR is explictly asked by user.

PR should have a clean commit history.
If unrelated commits are present on the branch, create a new branch with a clean history and open PR on that branch.  
  
Before opening a PR, review the diff against the main branch for correctness, style, regressions, and missing validation. If high risk issues are detected, stop and report them.  
  
If CI checks are defined in the repository:
- Test changes against them.
- Fix code until all checks are passed.
- If fixes impact code logic, architecture or become too large, stop and report them.
- Commit fixes.

Push branch then propose title and decription.  
PR will manually be opened by the user on Github.
