# Spec: TASK-CAR-INGESTION

> Example task specification — demonstrates the spec-driven workflow

## Summary

Lambda function to ingest a feed of cars from JSON files into DynamoDB.

## Requirements

| ID | Requirement |
|----|-------------|
| FR-001 | Lambda function must parse JSON car feed from S3 |
| FR-002 | Validate car data using Pydantic (make, model, year, price, vin) |
| FR-003 | Write valid cars to DynamoDB `cars` table |
| FR-004 | Log errors for invalid records with field-level detail |
| FR-005 | Unit tests with 100% coverage |
| FR-006 | README documentation |

> Mark anything unclear as `[NEEDS CLARIFICATION]` — do not guess.

## Technical Details

- **Language:** Python 3.11
- **Location:** `src/handlers/car_ingestion.py`
- **Dependencies:** boto3, pydantic

## Input/Output

**Input:** JSON file with array of car objects
```json
[
  {"make": "Toyota", "model": "Camry", "year": 2024, "price": 28000, "vin": "ABC123"}
]
```

**Output:** Cars written to DynamoDB `cars` table

## Edge Cases

- Empty JSON array (should succeed with 0 records written)
- Duplicate VIN in same batch (should log warning, write first occurrence)
- Missing required fields (should log error per record, continue processing)

## Testing

- [ ] Unit tests with 100% coverage
- [ ] Mock AWS services (S3, DynamoDB) using moto

---

## Generate

**AI, please:**

1. Read `docs/CONSTITUTION.md` — these rules are non-negotiable
2. Generate `docs/plans/TASK-CAR-INGESTION.md` with phased plan
   - Mark independent tasks with `[P]` for parallel execution
3. Generate `docs/prompts/TASK-CAR-INGESTION-P0-CORE.md` for first phase

Then at the end of **each phase**:

4. Generate `docs/sums/TASK-CAR-INGESTION-P{X}-{PHASE}.md` with phase summary
5. Generate `docs/prompts/TASK-CAR-INGESTION-P{X+1}-{PHASE}.md` for next phase
6. Update `CLAUDE.md` current state table

Follow the protocol in `CLAUDE.md`.
