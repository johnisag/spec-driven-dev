# Documentation

## Structure

```
docs/
├── README.md           # This file
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

| Folder | Who Creates | Purpose |
|--------|-------------|---------|
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
    [You work]
        │
        ▼
sums/TASK-FOO-P0-*.md      # AI generates summary
        │
        ▼
prompts/TASK-FOO-P1-*.md   # AI generates next prompt
        │
        ▼
    [Repeat]
```
