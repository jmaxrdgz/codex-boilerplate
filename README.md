# Persistent Codex Workflow

This repo uses a persistent Codex workflow inspired by this post on X:  
https://x.com/kareldoostrlnck/status/2019477361557926281

Codex stores notes, memory, and helper scripts in `.codex/` so it improves over time on this codebase.

Git acts as Codex's long-term memory.

---

# Setup (once per repo)

Copy these files into the repo root:

```

AGENTS.md
.codex/

````

Commit them:

```bash
git add AGENTS.md .codex
git commit -m "add Codex persistent workflow"
````

---

# Workflow (per task)

Create a new worktree:

```bash
git switch main
git pull
git worktree add ../repo--my-task -b my-task-branch
```

Open it in a separate VSCode window:

```bash
code ../repo--my-task
```

Work with Codex inside that folder.

---

# What Codex does automatically

* reads `.codex/memory/` and `.codex/helpers/`
* logs tasks in `.codex/inbox/`
* updates memory when learning durable info
* creates helpers when useful
* commits notes with code changes

Over time, Codex becomes faster and more reliable on this repo.

---

# Todo
- [ ] CRITICAL Update REAME.md with actual structure and need for a agent-docs branch !
- [ ] Decide on and implement a structured way for Codex to orchestrate specialized subagent roles so complex tasks can be delegated and parallelized reliably.
- [ ] Better use of plan mode (custom plan mode ?)
- [ ] Automatically generate a todo with discovered medium-low risk issues