# Spec-Driven Development

A lightweight framework for AI-assisted development using structured specs, plans, and phase-based execution.

## What Is This?

Spec-driven development is a workflow where:

1. **You write a brief spec** (requirements, constraints)
2. **AI generates the plan** (phases, deliverables, architecture)
3. **You execute phase by phase** (with AI assistance)
4. **AI generates summaries and next prompts** (maintaining context across sessions)

This creates a clear paper trail and ensures context is never lost between AI sessions.

## Why Use This?

- **No context loss** — Each phase prompt contains everything needed to continue
- **Clear handoffs** — Switch between AI tools (Claude, GPT, Copilot) seamlessly
- **Traceable decisions** — Architecture and decisions are documented as you go
- **Scales from small to large** — Same workflow for a bug fix or a full MVP

## The Workflow

```
┌─────────────────────────────────────────────────────────────────┐
│  YOU WRITE                        AI GENERATES                  │
│  ──────────                       ────────────                  │
│                                                                 │
│  docs/specs/TASK-FOO.md    ───►   docs/plans/TASK-FOO.md        │
│  (requirements)                   (phased plan)                 │
│                                                                 │
│                            ───►   docs/prompts/TASK-FOO-P0-*.md │
│                                   (first phase prompt)          │
│                                                                 │
│  [You work on Phase 0]                                          │
│                                                                 │
│                            ───►   docs/sums/TASK-FOO-P0-*.md    │
│                                   (what was done)               │
│                                                                 │
│                            ───►   docs/prompts/TASK-FOO-P1-*.md │
│                                   (next phase prompt)           │
│                                                                 │
│  [Repeat until complete]                                        │
└─────────────────────────────────────────────────────────────────┘
```

## Folder Structure

```
spec-driven-dev/
├── .github/
│   └── copilot-instructions.md    # For GitHub Copilot
├── .gitignore
├── .mcp.json                      # MCP server configs (Context7, etc.)
├── CLAUDE.md                      # Entry point + protocol
├── README.md                      # This file
│
└── docs/
    ├── README.md                  # Docs overview
    ├── CONSTITUTION.md            # Non-negotiable rules for AI agents
    ├── ARCHITECTURE.md            # System design (AI generates for PROJ-)
    │
    ├── specs/                     # YOU write these
    │   ├── _TEMPLATE-PROJ.md      # Full project/MVP
    │   ├── _TEMPLATE-FEAT.md      # New feature
    │   ├── _TEMPLATE-TASK.md      # Small task
    │   ├── _TEMPLATE-FIX.md       # Bug fix
    │   └── _EXAMPLE-TASK.md       # Example spec
    │
    ├── plans/                     # AI generates these
    │   └── _EXAMPLE-TASK.md       # Example plan
    │
    ├── prompts/                   # AI generates these
    │   ├── _EXAMPLE-TASK-P0.md    # Example Phase 0 prompt
    │   └── _EXAMPLE-TASK-P1.md    # Example Phase 1 prompt
    │
    └── sums/                      # AI generates these
        └── _EXAMPLE-TASK-P0.md    # Example Phase 0 summary
```

## Naming Conventions

| Prefix | Use For | Typical Phases |
|--------|---------|----------------|
| `PROJ-` | Full project/MVP | 5-10+ |
| `FEAT-` | New feature | 2-5 |
| `TASK-` | Small task | 1-3 |
| `FIX-` | Bug fix | 1 |

### File Naming

```
specs/PROJ-MVP.md                    # Your spec
plans/PROJ-MVP.md                    # Generated plan
prompts/PROJ-MVP-P0-SETUP.md         # Phase 0 prompt
sums/PROJ-MVP-P0-SETUP.md            # Phase 0 summary
prompts/PROJ-MVP-P1-DESIGN.md        # Phase 1 prompt
sums/PROJ-MVP-P1-DESIGN.md           # Phase 1 summary
```

## Getting Started

### 1. Copy this template

```bash
# Clone or use as GitHub template
git clone https://github.com/johnisag/spec-driven-dev.git my-project
cd my-project
rm -rf .git && git init
```

### 2. Write your first spec

```bash
# Copy the appropriate template
cp docs/specs/_TEMPLATE-TASK.md docs/specs/TASK-MY-TASK.md

# Edit with your requirements
```

### 3. Generate the plan

Open your AI assistant (Claude, ChatGPT, etc.) and say:

> "Read CLAUDE.md for context, then read the spec at docs/specs/TASK-MY-TASK.md and generate the plan."

### 4. Execute phases

Work through each phase. At the end of each phase, the AI generates:
- **Summary** of what was done (`docs/sums/`)
- **Prompt** for the next phase (`docs/prompts/`) — includes context from the summary

### 5. Continue until done

Each new session: read the latest prompt from `docs/prompts/`, paste into AI, continue working.

## The Protocol

At the end of **every phase**, AI must:

1. **Generate Summary** → `docs/sums/{TYPE}-{NAME}-P{X}-{PHASE}.md`
2. **Generate Next Prompt** → `docs/prompts/{TYPE}-{NAME}-P{X+1}-{PHASE}.md`
   - Must include relevant context from the summary
3. **Update CLAUDE.md** → Current state section
4. **Update README.md** → If user-facing changes
5. **Do not hallucinate** → Only reference existing files/work

See [CLAUDE.md](./CLAUDE.md) for the full protocol.

## Examples

Check the `_EXAMPLE-*` files in each folder to see the workflow in action:

- [Example Spec](./docs/specs/_EXAMPLE-TASK.md)
- [Example Plan](./docs/plans/_EXAMPLE-TASK.md)
- [Example Phase 0 Prompt](./docs/prompts/_EXAMPLE-TASK-P0.md)
- [Example Phase 0 Summary](./docs/sums/_EXAMPLE-TASK-P0.md)
- [Example Phase 1 Prompt](./docs/prompts/_EXAMPLE-TASK-P1.md)

## MCP Servers

The `.mcp.json` file includes recommended MCP servers for AI coding assistants:

| Server | Purpose | Config Needed |
|--------|---------|---------------|
| **Context7** | Up-to-date library docs in AI context | None (zero-config) |

To add the GitHub MCP server for issues/PRs integration, add to `.mcp.json`:

```json
"github": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-github"],
  "env": { "GITHUB_PERSONAL_ACCESS_TOKEN": "your-token-here" }
}
```

## License

MIT — Use freely, attribution appreciated.

---

_Ship fast. Learn faster._
