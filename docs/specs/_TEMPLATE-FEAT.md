# Spec: FEAT-[NAME]

> New feature specification

## Summary

[One sentence: What feature and why?]

## Context

[What exists today? What problem does this solve?]

## Requirements

- [ ] [Requirement 1]
- [ ] [Requirement 2]
- [ ] [Requirement 3]

## Technical Approach

- **Affected components:** [e.g., API, Database, UI]
- **New dependencies:** [e.g., None, Stripe SDK]
- **Database changes:** [e.g., New table, migration needed]

## Non-Goals

- [What this feature does NOT include]

## Testing

- [ ] Unit tests
- [ ] Integration tests

---

## Generate

**AI, please:**

1. Update `docs/ARCHITECTURE.md` if needed
2. Generate `docs/plans/FEAT-[NAME].md` with phased plan
3. Generate `docs/prompts/FEAT-[NAME]-P0-{PHASE}.md` for first phase

Then at the end of **each phase**:

4. Generate `docs/sums/FEAT-[NAME]-P{X}-{PHASE}.md` with phase summary
5. Generate `docs/prompts/FEAT-[NAME]-P{X+1}-{PHASE}.md` for next phase
6. Update `CLAUDE.md` current state table

Follow the protocol in `CLAUDE.md`.
