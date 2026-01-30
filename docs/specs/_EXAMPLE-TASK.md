# Spec: TASK-CAR-INGESTION

> Example task specification — demonstrates the spec-driven workflow

## Summary

Lambda function to ingest a feed of cars from JSON files into DynamoDB.

## Requirements

- [ ] Lambda function to parse JSON car feed
- [ ] Validate car data using Pydantic
- [ ] Write valid cars to DynamoDB
- [ ] Log errors for invalid records
- [ ] Unit tests with 100% coverage
- [ ] Documentation

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

## Testing

- [ ] Unit tests with 100% coverage
- [ ] Mock AWS services (S3, DynamoDB)

---

## Generate

**AI, please:**

1. Generate `docs/plans/TASK-CAR-INGESTION.md` with phased plan
2. Generate `docs/prompts/TASK-CAR-INGESTION-P0-CORE.md` for first phase

Then at the end of **each phase**:

3. Generate `docs/sums/TASK-CAR-INGESTION-P{X}-{PHASE}.md` with phase summary
4. Generate `docs/prompts/TASK-CAR-INGESTION-P{X+1}-{PHASE}.md` for next phase
5. Update `CLAUDE.md` current state table

Follow the protocol in `CLAUDE.md`.
