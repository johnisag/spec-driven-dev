# Tooling Guide

> Optional tools that enhance the spec-driven workflow. None are required — the framework works with just markdown and any AI assistant.

---

## Beads — Multi-Agent Task Graph

**What:** Git-backed dependency-aware task tracker built for AI coding agents.
**Repo:** https://github.com/steveyegge/beads
**When to use:** `PROJ-` work with many phases, or when multiple agents work in parallel.

### Why It Fits

| Framework Concept | Beads Equivalent |
|-------------------|------------------|
| "Next Prompt" in CLAUDE.md | `bd ready` — shows unblocked tasks |
| Phase dependencies | Dependency graph with `blocks` edges |
| Manual phase transitions | Automatic unblocking when tasks close |
| Single-agent workflow | `bd update --claim` for multi-agent coordination |

### Setup

```bash
# Install (Go required, or download binary from releases)
go install github.com/steveyegge/beads/cmd/bd@latest

# Initialize in your project
bd init

# Set up Claude integration
bd setup claude
```

### Workflow With This Framework

**Plan generation** — When AI generates a plan, also create Beads tasks:

```bash
# Create parent task from spec
bd create "PROJ-MVP" --label epic

# Create phase tasks with dependencies
bd create "P0: Setup" --parent <epic-id>
bd create "P1: Core" --parent <epic-id>
bd dep add <P1-id> <P0-id>   # P1 blocked until P0 done
```

**Phase execution** — Instead of checking CLAUDE.md for next prompt:

```bash
bd ready              # What can I work on now?
bd update <id> --claim  # Claim a task (prevents agent conflicts)
bd close <id>          # Mark done → unblocks dependents
```

**Parallel work** — Mark independent tasks with `[P]` in your plan, create them without `blocks` dependencies. Multiple agents can claim and work on them simultaneously.

### When NOT to Use Beads

- `TASK-` and `FIX-` items (1-3 phases) — the markdown workflow is simpler
- Solo developer on small features — overhead isn't justified
- Teams unfamiliar with git-based tooling

---

## Qodo — AI Code Review Quality Gate

**What:** Multi-agent code review platform that validates implementation against specs.
**Site:** https://www.qodo.ai
**When to use:** End of each phase, before generating the summary.

### Why It Fits

The end-of-phase protocol generates a summary claiming deliverables are complete. Qodo validates that claim by reviewing the actual code against requirements.

### Integration

Add a quality check step **before** the end-of-phase protocol:

```
[Phase work complete]
        │
        ▼
  Run quality check ← NEW (optional)
        │
        ▼
  Generate summary
        │
        ▼
  Generate next prompt
```

**In practice:**
1. Install the Qodo VS Code extension or CLI
2. After completing phase deliverables, run a review
3. Fix any issues flagged
4. Then proceed with the end-of-phase protocol

### What to Check

| Check | Tools |
|-------|-------|
| Code matches spec requirements | Qodo review, manual check |
| Tests pass | `npm test`, `pytest`, etc. |
| No regressions | Run full test suite |
| Linting clean | ESLint, Ruff, etc. |

---

## File Separation for Large Projects

For `PROJ-` specs with complex data models or API contracts, consider splitting into separate files instead of one large spec.

### Standard Structure (default)

```
docs/specs/PROJ-MVP.md          # Everything in one file
```

### Extended Structure (for complex projects)

```
docs/specs/PROJ-MVP.md          # Core spec (vision, requirements, acceptance criteria)
docs/specs/PROJ-MVP-DATA.md     # Data model definitions
docs/specs/PROJ-MVP-API.md      # API contracts and endpoints
docs/specs/PROJ-MVP-RESEARCH.md # Technical investigation notes
```

### When to Split

- Spec exceeds ~200 lines
- Multiple distinct domains (data model, API, UI) that benefit from separate review
- Technical research needed before planning (capture in RESEARCH.md)

### How to Reference

In your main spec, add a "Related Files" section:

```markdown
## Related Files

- `docs/specs/PROJ-MVP-DATA.md` — Data model definitions
- `docs/specs/PROJ-MVP-API.md` — API contracts
```

In the Generate section, tell the AI to read them:

```markdown
1. Read `docs/CONSTITUTION.md`
2. Read `docs/specs/PROJ-MVP-DATA.md` and `docs/specs/PROJ-MVP-API.md`
3. Generate plan...
```

---

## Tool Comparison

| Need | Tool | Effort |
|------|------|--------|
| Current library docs in AI context | Context7 MCP (`.mcp.json`) | Zero config |
| GitHub issues/PRs from AI | GitHub MCP server | Needs PAT |
| Multi-agent task coordination | Beads | Medium setup |
| Code quality gate | Qodo | Extension install |
| Complex spec organization | File separation | Just markdown |

---

_All tools are optional. The framework works without any of them._
