# Spec: PROJ-[NAME]

> Full project or MVP specification

## Vision

[What are you building and why? 2-3 sentences]

## Target Users

- [User type 1]: [Their need]
- [User type 2]: [Their need]

## Core Features

- [ ] [Feature 1]
- [ ] [Feature 2]
- [ ] [Feature 3]

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

## Non-Goals

- [What you're NOT building]

## Technical Requirements

- **Language/Framework:** [e.g., Next.js 14, TypeScript]
- **Database:** [e.g., PostgreSQL, none for MVP]
- **Hosting:** [e.g., Vercel, AWS]

## Constraints

- [Time: e.g., MVP in 2 weeks]
- [Budget: e.g., Free tier only]
- [Technical: e.g., Must work offline]

## Success Criteria

| ID | Metric | Target |
|----|--------|--------|
| SC-001 | [e.g., Page load time] | [e.g., < 2s] |
| SC-002 | [e.g., Test coverage] | [e.g., > 80%] |

## Edge Cases

- [Boundary condition or error scenario 1]
- [Boundary condition or error scenario 2]

---

## Generate

**AI, please:**

1. Read `docs/CONSTITUTION.md` — these rules are non-negotiable
2. Generate `docs/ARCHITECTURE.md` with system design
3. Generate `docs/plans/PROJ-[NAME].md` with phased development plan
   - Mark independent tasks with `[P]` for parallel execution
4. Generate `docs/prompts/PROJ-[NAME]-P0-SETUP.md` for first phase

Then at the end of **each phase**:

5. Generate `docs/sums/PROJ-[NAME]-P{X}-{PHASE}.md` with phase summary
6. Generate `docs/prompts/PROJ-[NAME]-P{X+1}-{PHASE}.md` for next phase
7. Update `CLAUDE.md` current state table

Follow the protocol in `CLAUDE.md`.
