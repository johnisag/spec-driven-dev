# Project: [PROJECT NAME]

> **Quick Start:** Read this file first, then check `docs/prompts/` for your current task.

---

## Current State

| Field | Value |
|-------|-------|
| **Active Work** | [None yet] |
| **Current Phase** | [N/A] |
| **Next Prompt** | [None yet] |
| **Last Updated** | [Date] |

---

## Project Overview

[Brief description - 2-3 sentences max. Delete this section if not a PROJ-]

## Tech Stack

- [Language/Framework]
- [Database]
- [Other key tech]

## Quick Commands

```bash
# Development
npm run dev        # Start dev server
npm run build      # Production build
npm run test       # Run tests
```

---

## Documentation Map

| Location | Purpose | Who Creates |
|----------|---------|-------------|
| `CLAUDE.md` | Entry point, current state, protocol | You + AI updates |
| `docs/ARCHITECTURE.md` | System design, components, decisions | AI generates |
| `docs/specs/` | Requirements and briefs | **You write** |
| `docs/plans/` | Development plans with phases | AI generates |
| `docs/prompts/` | Phase prompts with context | AI generates |
| `docs/sums/` | Phase summaries | AI generates |

---

## End of Phase Protocol

### ⚠️ IMPORTANT — AI MUST DO THIS AT THE END OF EVERY PHASE

#### 1. Generate Summary

**Location:** `docs/sums/{TYPE}-{NAME}-P{X}-{PHASE-NAME}.md`

**Must Include:**
- Date completed
- What was done (deliverables completed)
- Decisions made and rationale
- Any issues encountered
- What's ready for next phase

#### 2. Generate Next Phase Prompt

**Location:** `docs/prompts/{TYPE}-{NAME}-P{X+1}-{PHASE-NAME}.md`

**Must Include:**
- Context from previous phase summary (key points, not full copy)
- Current state of the codebase
- Clear deliverables for this phase
- Exit criteria
- Files to reference
- The IMPORTANT section (copy from below)

#### 3. Update CLAUDE.md

Update the "Current State" table at the top:
- Active Work → Current task name
- Current Phase → Phase number and name
- Next Prompt → Path to next prompt file
- Last Updated → Today's date

#### 4. Update README.md

If there are user-facing changes (new features, changed behavior), update the project README.

#### 5. Do Not Hallucinate

- Only reference files that actually exist
- Only claim completion of work actually done
- If uncertain, ask for clarification
- Verify file paths before referencing them

---

## Naming Conventions

### Type Prefixes

| Prefix | Use For | Typical Size |
|--------|---------|--------------|
| `PROJ-` | Full project/MVP build | 5-10+ phases |
| `FEAT-` | New feature | 2-5 phases |
| `TASK-` | Small unit of work | 1-3 phases |
| `FIX-` | Bug fix | 1 phase |

### File Naming Pattern

```
{TYPE}-{NAME}-P{PHASE}-{PHASE-NAME}.md

Examples:
PROJ-MVP-P0-SETUP.md
PROJ-MVP-P1-DESIGN-SYSTEM.md
FEAT-USER-AUTH-P0-DATABASE.md
TASK-CAR-INGESTION-P0-CORE.md
FIX-SEARCH-BUG-P0-FIX.md
```

---

## Workflow

```
YOU                                     AI
───                                     ──

1. Write spec
   docs/specs/{TYPE}-{NAME}.md
                                    2. Generate plan
                                       docs/plans/{TYPE}-{NAME}.md
                                    
                                    3. Generate architecture (if PROJ-)
                                       docs/ARCHITECTURE.md
                                    
                                    4. Generate first prompt
                                       docs/prompts/{TYPE}-{NAME}-P0-*.md

5. Work on Phase 0
   (with AI assistance)
                                    6. Generate Phase 0 summary
                                       docs/sums/{TYPE}-{NAME}-P0-*.md
                                    
                                    7. Generate Phase 1 prompt
                                       docs/prompts/{TYPE}-{NAME}-P1-*.md
                                    
                                    8. Update CLAUDE.md

9. [New session] Read Phase 1 prompt
   Continue working...
                                    10. Repeat until done
```

---

## Starting a New Task

1. Copy appropriate template from `docs/specs/_TEMPLATE-*.md`
2. Fill in your requirements
3. Ask AI: *"Read CLAUDE.md, then read docs/specs/[your-spec].md and generate the plan"*

## Continuing Work

1. Check "Current State" table above for next prompt location
2. Read the prompt file
3. Paste into AI session
4. Continue working

---

## Key Decisions Log

| Decision | Rationale | Date |
|----------|-----------|------|
| [Example] | [Why] | [When] |

---

_Ship fast. Learn faster._
