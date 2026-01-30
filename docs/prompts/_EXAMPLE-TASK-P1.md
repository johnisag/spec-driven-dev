# Prompt: TASK-CAR-INGESTION-P1-TESTING

> Phase 1 of 1 (Final) | Task: Car Ingestion Lambda

---

## Context

**Spec:** `docs/specs/_EXAMPLE-TASK.md`  
**Plan:** `docs/plans/_EXAMPLE-TASK.md`  
**Previous Summary:** `docs/sums/TASK-CAR-INGESTION-P0-CORE.md`

---

## Previous Phase Summary

**Phase 0 completed** — Core implementation done:

- ✅ `src/handlers/car_ingestion.py` — Lambda handler with S3 trigger, batch DynamoDB writes
- ✅ `src/models/car.py` — Pydantic v2 model with validation (year >= 1900, price > 0, vin = 17 chars)
- ✅ Error handling — Invalid records logged, don't stop processing

**Key decisions made:**
- Batch writes of 25 (DynamoDB max)
- Continue processing on validation errors
- Table name from environment variable

---

## Phase 1 Goal

Achieve 100% test coverage and complete documentation.

---

## Deliverables

- [ ] Unit tests (`src/tests/test_car_ingestion.py`)
  - Test valid car parsing
  - Test invalid car handling (bad year, price, vin)
  - Test batch write logic
  - Test S3 event parsing
  - Test DynamoDB error handling
- [ ] Mocked AWS services using `moto`
- [ ] Coverage report showing 100%
- [ ] Docstrings on all public functions
- [ ] README section documenting:
  - How to deploy
  - Environment variables needed
  - Expected input format

---

## Exit Criteria

- [ ] All tests pass
- [ ] Coverage at 100%
- [ ] No functions without docstrings
- [ ] README updated

---

## Technical Notes

- Use `pytest` + `moto` for testing
- Use `pytest-cov` for coverage
- Mock both S3 and DynamoDB

---

## Files to Reference

- `src/handlers/car_ingestion.py` — Handler to test
- `src/models/car.py` — Model to test
- `docs/specs/_EXAMPLE-TASK.md` — Sample data format

---

## IMPORTANT

At the end of this phase:
1. Generate summary → `docs/sums/TASK-CAR-INGESTION-P1-TESTING.md`
2. This is the final phase — no next prompt needed
3. Update `CLAUDE.md`:
   - Active Work → "None"
   - Note task completion
4. Update `README.md` with Lambda documentation
5. Do not hallucinate
