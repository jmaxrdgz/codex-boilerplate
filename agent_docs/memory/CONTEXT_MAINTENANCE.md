# Context Maintenance Guide

Keep AI context focused on **actionable, current information** while archiving **historical details** for reference.
**Principle**: Answer "What am I working on **now**?" not "What did we do 6 months ago?"

---

## File Organization Hierarchy

### Tier 1: Critical (Always Loaded)
Essential for every session, remain lean:

- **@agent_docs/memory/PROJECT_CONTEXT.md** - High-level overview (~200 lines)
- **@agent_docs/memory/TODO.md** - Active tasks only (~300 lines)

### Tier 2: Technical Reference (Always Loaded)
Essential for daily work:
- **@agent_docs/rules/CONTRIBUTING.md** - Coding guidelines
- **@agent_docs/rules/RULES.md** - Agent rules
- **@README.md**
- **@agent_docs/rules/CONTRIBUTING.md**
- **@agent_docs/rules/RULES.md**

### Tier 3: Design Docs (Load On-Demand)
Load when working on specific subsystems:

### Tier 4: Historical Archive (Load Rarely)
Reference for past decisions:

- @agent_docs/memory/COMPLETED.md
- @agent_docs/memory/archive/* (handoffs, analyses, build proposals, cleanups)

---

## Maintenance Schedule

### After Major Milestone
1. Move completion notes from TODO.md to COMPLETED.md
2. Update PROJECT_CONTEXT.md "Current Status"
3. Archive detailed plans from TODO.md
4. Update "Next Up" section

### Monthly Review
1. Archive tasks completed >30 days ago
2. Remove old "Recently Completed" items
3. Move temp analysis docs to agent_docs/
4. Verify agent configs load only Tier 1-2

### On-Demand (Context Bloat)
1. Check for oversized files (>500 lines in Tier 1-2)
2. Archive verbose sections
3. Split large design docs

---

## Decision Matrix: What to Archive?

| Content Type | Action | Keep in Main Docs |
|--------------|--------|------------------|
| Completed tasks (>30 days) | ✅ Archive | 2-line summary |
| Detailed plans (>100 lines) | ✅ Archive | Goal + approach |
| Analysis of resolved issues | ✅ Archive | Root cause + solution |
| Deprecated designs | ✅ Archive | Pointer to archive |
| Major architectural decisions | ⚠️ Summarize | 3-line summary |
| Performance optimizations | ⚠️ Summarize | Before/after metrics |
| Current priorities | ❌ Keep | Full details |
| Coding guidelines | ❌ Keep | Full details |
| Active constraints | ❌ Keep | Full details |

**Quick rule**: If >30 days old AND >50 lines of detail → Archive with 2-line summary.

---

## Red Flags (Clean Up Now)

### File Size
- PROJECT_CONTEXT.md >500 lines (critical: >800)
- TODO.md >800 lines (critical: >1200)
- Any Tier 1-2 file >1000 lines

### Content
- "Recently Completed" >100 lines in PROJECT_CONTEXT.md
- TODO.md has tasks marked `[DONE]` >30 days ago
- Detailed plans (>50 lines) for completed tasks
- Analysis docs in root directory (move to ai_agent_doc/)

### Performance
- AI responses noticeably slower
- Token usage >50K on initial load
- Repeated "let me read..." for basic info

---

## Archiving Workflow

**Quick steps:**
1. Find content: `grep -n "\[x\].*202[0-9]" TODO.md`
2. Move to COMPLETED.md with format:
   ```markdown
   - [x] **Task Name**: Brief summary (2-3 bullets max, one-line result)
   ```
3. Replace verbose sections: `**Note**: See @agent_docs/COMPLETED.md`
4. Update agent configs if files moved
5. Verify: `grep -r "@doc/" CLAUDE.md AGENTS.md`

**File moves:**
```bash
git mv OLDFILE.md agent_docs/OLDFILE.md
# Update CLAUDE.md/AGENTS.md references
# Update cross-references: grep -r "OLDFILE.md" *.md agent_docs/*.md
git commit -m "docs: Move OLDFILE.md to agent_docs/"
```

---

## Context Size Targets

| File | Optimal | Warning | Critical |
|------|---------|---------|----------|
| CLAUDE.md/AGENTS.md | <30 lines | - | - |
| PROJECT_CONTEXT.md | <300 lines | >500 | >800 |
| TODO.md | <500 lines | >800 | >1200 |
| Total Tier 1-2 | <10K words | >15K | >20K |

---

## Examples

### Good: Lean TODO.md
```markdown
- [ ] **Task #72: Model size reduction **
    - Goal: Reduce .onnx sizes by 50%
    - Approach: 4b quantization
    - See: agent_docs/MODELS_FILES.md
```

### Bad: Verbose TODO.md
```markdown
- [ ] **Task #72: Model size reduction **
    - Goal: Reduce .onnx sizes by 50%
    - Background: float32 wasteful... [20 lines]
    - Step 1: Create interface
      - Define QuantizerBase [100+ lines]
```

### Good: Lean PROJECT_CONTEXT.md

### Bad: Verbose PROJECT_CONTEXT.md

---

## Common Mistakes

### ❌ Don't:
- Archive active tasks or priorities
- Remove essential architectural context
- Break cross-references without updating
- Delete content (archive instead)
- Keep "Recently Completed" >3 months

### ✅ Do:
- Preserve key insights in summaries
- Update file references after moves
- Keep audit trail (note where moved)
- Regular small cleanups (not big purges)

---

## Quick Decision Test

If unsure whether to archive:

1. Completed >30 days ago? → Archive
2. Detailed plan (>50 lines)? → Archive (keep 2-line summary)
3. Needed next week? → Keep
4. New contributor needs immediately? → Keep

When in doubt, **archive with pointer**. Better clean context than bloat.