# Documentation

## Structure

```
docs/
├── README.md           # This file
├── CONSTITUTION.md     # Non-negotiable rules for AI agents
├── TOOLING.md          # Optional tools: Beads, Qodo, multi-agent
├── ARCHITECTURE.md     # System design (AI generates for PROJ-)
│
├── specs/              # Specifications — YOU write these
│   ├── _TEMPLATE-PROJ.md
│   ├── _TEMPLATE-FEAT.md
│   ├── _TEMPLATE-TASK.md
│   ├── _TEMPLATE-FIX.md
│   └── _EXAMPLE-TASK.md
│
├── plans/              # Development plans — AI generates
│   └── _EXAMPLE-TASK.md
│
├── prompts/            # Phase prompts — AI generates
│   ├── _EXAMPLE-TASK-P0.md
│   └── _EXAMPLE-TASK-P1.md
│
└── sums/               # Phase summaries — AI generates
    └── _EXAMPLE-TASK-P0.md
```

## What Goes Where

| File/Folder | Who Creates | Purpose |
|-------------|-------------|---------|
| `CONSTITUTION.md` | **You** + AI | Non-negotiable rules all AI agents must follow |
| `specs/` | **You** | Requirements, constraints, what you want built |
| `plans/` | AI | Phased development plan with deliverables |
| `prompts/` | AI | Context + instructions for each phase |
| `sums/` | AI | Summary of completed work per phase |

## Naming Convention

```
{TYPE}-{NAME}.md                         # specs, plans
{TYPE}-{NAME}-P{X}-{PHASE-NAME}.md       # prompts, sums

TYPE = PROJ | FEAT | TASK | FIX
```

## Examples

See the `_EXAMPLE-*` files in each folder for a complete worked example of a `TASK-` workflow.

## The Flow

```
specs/TASK-FOO.md          # You write requirements
        │
        ▼
plans/TASK-FOO.md          # AI generates phased plan
        │
        ▼
prompts/TASK-FOO-P0-*.md   # AI generates first prompt
        │
        ▼
    [You work on Phase 0]
        │
        ▼
sums/TASK-FOO-P0-*.md      # AI generates summary
        │
        ▼
prompts/TASK-FOO-P1-*.md   # AI generates next prompt
        │
        ▼
sums/TASK-FOO-P1-*.md      # AI generates summary
        │
        ▼
    [Repeat until complete]
```

## End of Phase Checklist

At the end of **every phase**, AI must:

1. ✅ Generate summary → `docs/sums/{TYPE}-{NAME}-P{X}-{PHASE}.md`
2. ✅ Generate next prompt → `docs/prompts/{TYPE}-{NAME}-P{X+1}-{PHASE}.md`
3. ✅ Update `CLAUDE.md` current state table
4. ✅ Update project `README.md` if user-facing changes
5. ✅ Verify all referenced files exist (no hallucination)
