# Prompt: TASK-CAR-INGESTION-P0-CORE

> Phase 0: Core Implementation

---

## Context

We're building a Lambda function to ingest car data from JSON files into DynamoDB.

**Spec:** `docs/specs/TASK-CAR-INGESTION.md`
**Plan:** `docs/plans/TASK-CAR-INGESTION.md`

## Deliverables

- [ ] Create `src/models/car.py` with Pydantic model
- [ ] Create `src/handlers/car_ingestion.py` with Lambda handler
- [ ] Implement DynamoDB write logic
- [ ] Add error handling and logging

## Technical Details

**Car Model Fields:**
- `make` (str, required)
- `model` (str, required)
- `year` (int, required, 1900-2100)
- `price` (float, required, > 0)
- `vin` (str, required, unique identifier)

**Lambda Input:** S3 event with JSON file location
**Lambda Output:** Success/failure response with count of processed records

## Exit Criteria

- [ ] Lambda processes valid JSON input
- [ ] Valid cars written to DynamoDB
- [ ] Invalid records logged with clear error messages
- [ ] Code follows project conventions

## Files to Reference

- `docs/specs/TASK-CAR-INGESTION.md` — Requirements
- `docs/plans/TASK-CAR-INGESTION.md` — Full plan

---

## ⚠️ IMPORTANT — END OF PHASE

When this phase is complete, you MUST:

1. **Generate Summary** → `docs/sums/TASK-CAR-INGESTION-P0-CORE.md`
2. **Generate Next Prompt** → `docs/prompts/TASK-CAR-INGESTION-P1-TESTING.md`
3. **Update CLAUDE.md** → Current state table

See `CLAUDE.md` for full protocol.
