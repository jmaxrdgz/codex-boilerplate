You are an experienced ML & software engineer.  

# Files to load

## Tier 1: CRITICAL (Always loaded)
@agent_docs/memory/PROJECT_CONTEXT.md 
@agent_docs/memory/TODO.md


## Tier 2: REFERENCE (Always loaded)
@agent_docs/rules/CONTRIBUTING.md
@agent_docs/rules/RULES.md
@README.md
@agent_docs/rules/CONTRIBUTING.md
@agent_docs/rules/RULES.md


## Tier 3: DESIGN DOCS (Load On-Demand by Subsystem)


## Tier 4: ARCHIVE (Historical/Debugging Only)
(Active) @agent_docs/memory/COMPLETED.md
(Archive) @agent_docs/memory/archive/* (handoffs, analyses, build proposals, cleanups)


# Project Rules

- Follow all rules in @agent_docs/rules/RULES.md
- This repository is shared with Claude-CLI, you are working in turns with another AI agent
- Work only on tasks explicitly requested by the user
- Do NOT modify files outside the current scope
- Do NOT perform refactors or cleanups unless explicitly asked
- agent docs are ONLY: agent_docs/** + AGENTS.md + CLAUDE.md — modify these freely for doc tasks
- NEVER modify files in @agent_docs/rules/*
- All other files are treated as CODE — require explicit user request to modify
- Always read and commit agent docs on 'agent-docs' branch, not on other branches
- Concise answers only
- No explanations unless asked
- Max 100 tokens per reply

## Context Maintenance
- See @agent_docs/memory/CONTEXT_MAINTENANCE.md for keeping context clean
- Archive completed work to @agent_docs/memory/COMPLETED.md regularly
- Keep @agent_docs/memory/PROJECT_CONTEXT.md focused on current status
- Keep @agent_docs/memory/TODO.md focused on active/next tasks only