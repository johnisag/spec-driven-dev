# Spec: FEAT-[NAME]

> New feature specification

## Summary

[One sentence: What feature and why?]

## Context

[What exists today? What problem does this solve?]

## Requirements

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-001 | [System MUST ...] | P1 |
| FR-002 | [Users MUST be able to ...] | P1 |
| FR-003 | [System SHOULD ...] | P2 |

> Mark anything unclear as `[NEEDS CLARIFICATION]` — do not guess.

## Acceptance Criteria

### AC-001: [Scenario name]

- **Given** [precondition]
- **When** [action]
- **Then** [expected result]

### AC-002: [Scenario name]

- **Given** [precondition]
- **When** [action]
- **Then** [expected result]

## Technical Approach

- **Affected components:** [e.g., API, Database, UI]
- **New dependencies:** [e.g., None, Stripe SDK]
- **Database changes:** [e.g., New table, migration needed]

## Non-Goals

- [What this feature does NOT include]

## Edge Cases

- [Boundary condition or error scenario 1]
- [Boundary condition or error scenario 2]

## Testing

- [ ] Unit tests
- [ ] Integration tests

---

## Generate

**AI, please:**

1. Read `docs/CONSTITUTION.md` — these rules are non-negotiable
2. Update `docs/ARCHITECTURE.md` if needed
3. Generate `docs/plans/FEAT-[NAME].md` with phased plan
   - Mark independent tasks with `[P]` for parallel execution
4. Generate `docs/prompts/FEAT-[NAME]-P0-{PHASE}.md` for first phase

Then at the end of **each phase**:

5. Generate `docs/sums/FEAT-[NAME]-P{X}-{PHASE}.md` with phase summary
6. Generate `docs/prompts/FEAT-[NAME]-P{X+1}-{PHASE}.md` for next phase
7. Update `CLAUDE.md` current state table

Follow the protocol in `CLAUDE.md`.
