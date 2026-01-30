# Prompt: TASK-CAR-INGESTION-P0-CORE

> Phase 0 of 1 | Task: Car Ingestion Lambda

---

## Context

**Spec:** `docs/specs/_EXAMPLE-TASK.md`  
**Plan:** `docs/plans/_EXAMPLE-TASK.md`

**What we're building:**  
Lambda function to ingest car data from JSON into DynamoDB with Pydantic validation.

**Previous phases:** None (this is Phase 0)

---

## Phase 0 Goal

Build the core Lambda handler with data validation.

---

## Deliverables

- [ ] Project structure
  - `src/handlers/car_ingestion.py`
  - `src/models/car.py`
- [ ] Car Pydantic model with fields: make, model, year, price, vin
- [ ] Lambda handler that:
  - Reads JSON from S3 event
  - Validates each car record
  - Writes valid cars to DynamoDB
  - Logs invalid records (doesn't crash)
- [ ] Basic error handling

---

## Exit Criteria

- [ ] Lambda can parse sample JSON file
- [ ] Valid cars are written to DynamoDB
- [ ] Invalid records logged with details
- [ ] No unhandled exceptions

---

## Technical Notes

- Use Pydantic v2 for validation
- DynamoDB table name from environment variable
- Batch writes for performance (25 items max per batch)

---

## Files to Reference

- Sample data format in spec: `docs/specs/_EXAMPLE-TASK.md`

---

## IMPORTANT

At the end of this phase:
1. Generate summary → `docs/sums/TASK-CAR-INGESTION-P0-CORE.md`
2. Generate next prompt → `docs/prompts/TASK-CAR-INGESTION-P1-TESTING.md`
   - Include key context from the summary
3. Update `CLAUDE.md` current state
4. Do not hallucinate
