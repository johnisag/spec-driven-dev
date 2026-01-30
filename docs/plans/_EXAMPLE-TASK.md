# Plan: TASK-CAR-INGESTION

> Generated from spec: `docs/specs/_EXAMPLE-TASK.md`

## Overview

Lambda function to ingest car data from JSON files into DynamoDB with validation and error handling.

## Phases

### Phase 0: Core Implementation

**Goal:** Build the core Lambda handler with data validation

**Deliverables:**
- [ ] Project structure (`src/handlers/`, `src/models/`)
- [ ] Car Pydantic model with validation
- [ ] Lambda handler skeleton
- [ ] JSON parsing logic
- [ ] DynamoDB write logic
- [ ] Basic error handling

**Exit Criteria:**
- Lambda can parse sample JSON
- Valid cars written to DynamoDB
- Invalid records logged (not crash)

---

### Phase 1: Testing & Polish

**Goal:** Achieve 100% test coverage and documentation

**Deliverables:**
- [ ] Unit tests for all functions
- [ ] Mocked AWS services (moto)
- [ ] 100% coverage report
- [ ] Docstrings on all functions
- [ ] README section for this Lambda

**Exit Criteria:**
- All tests pass
- Coverage at 100%
- Documentation complete

---

## Technical Decisions

| Decision | Rationale |
|----------|-----------|
| Pydantic for validation | Type safety, clear error messages |
| Moto for AWS mocks | Standard practice, good DynamoDB support |
| Batch writes | Better performance than individual puts |

---

## File Structure (Target)

```
src/
├── handlers/
│   └── car_ingestion.py    # Lambda handler
├── models/
│   └── car.py              # Pydantic model
└── tests/
    └── test_car_ingestion.py
```

---

## IMPORTANT

At the end of each phase:
1. Generate summary → `docs/sums/TASK-CAR-INGESTION-P{X}-*.md`
2. Generate next prompt → `docs/prompts/TASK-CAR-INGESTION-P{X+1}-*.md`
   - Include context from the summary
3. Update `CLAUDE.md` current state
4. Update `README.md` if needed
5. Do not hallucinate
