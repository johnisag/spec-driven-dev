# Spec: TASK-[NAME]

> Small, focused task

## Summary

[One sentence: What needs to be done?]

## Requirements

| ID | Requirement |
|----|-------------|
| FR-001 | [Must ...] |
| FR-002 | [Must ...] |
| FR-003 | [Must ...] |

> Mark anything unclear as `[NEEDS CLARIFICATION]` — do not guess.

## Technical Details

- **Language:** [e.g., Python, TypeScript]
- **Location:** [e.g., src/handlers/]
- **Dependencies:** [e.g., boto3, none]

## Input/Output

**Input:** [What it receives]

**Output:** [What it produces]

## Edge Cases

- [Boundary condition or error scenario]

## Testing

- [ ] Unit tests
- [ ] [Coverage requirement if any]

---

## Generate

**AI, please:**

1. Read `docs/CONSTITUTION.md` — these rules are non-negotiable
2. Generate `docs/plans/TASK-[NAME].md` with phased plan
   - Mark independent tasks with `[P]` for parallel execution
3. Generate `docs/prompts/TASK-[NAME]-P0-{PHASE}.md` for first phase

Then at the end of **each phase**:

4. Generate `docs/sums/TASK-[NAME]-P{X}-{PHASE}.md` with phase summary
5. Generate `docs/prompts/TASK-[NAME]-P{X+1}-{PHASE}.md` for next phase
6. Update `CLAUDE.md` current state table

Follow the protocol in `CLAUDE.md`.
