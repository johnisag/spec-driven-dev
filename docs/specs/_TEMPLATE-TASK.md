# Spec: TASK-[NAME]

> Small, focused task

## Summary

[One sentence: What needs to be done?]

## Requirements

- [ ] [Requirement 1]
- [ ] [Requirement 2]
- [ ] [Requirement 3]

## Technical Details

- **Language:** [e.g., Python, TypeScript]
- **Location:** [e.g., src/handlers/]
- **Dependencies:** [e.g., boto3, none]

## Input/Output

**Input:** [What it receives]

**Output:** [What it produces]

## Testing

- [ ] Unit tests
- [ ] [Coverage requirement if any]

---

## Generate

**AI, please:**

1. Generate `docs/plans/TASK-[NAME].md` with phased plan
2. Generate `docs/prompts/TASK-[NAME]-P0-{PHASE}.md` for first phase

Then at the end of **each phase**:

3. Generate `docs/sums/TASK-[NAME]-P{X}-{PHASE}.md` with phase summary
4. Generate `docs/prompts/TASK-[NAME]-P{X+1}-{PHASE}.md` for next phase
5. Update `CLAUDE.md` current state table

Follow the protocol in `CLAUDE.md`.
