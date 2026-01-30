# Prompt: TASK-CAR-INGESTION-P1-TESTING

> Phase 1: Testing & Documentation

---

## Context

**Previous Phase:** P0-CORE completed on 2024-01-15

### What Was Done in Phase 0
- Created Pydantic Car model with validation
- Implemented Lambda handler with DynamoDB integration
- Used `batch_writer()` for performance
- Added structured JSON logging

### Current State
```
src/
├── models/
│   └── car.py           # ✅ Complete
└── handlers/
    └── car_ingestion.py # ✅ Complete
```

## Deliverables

- [ ] Create `src/tests/test_car_ingestion.py`
- [ ] Add moto for AWS service mocking
- [ ] Achieve 100% code coverage
- [ ] Create README with usage instructions
- [ ] Test error cases (invalid data, DynamoDB failures)

## Technical Details

**Testing Stack:**
- pytest
- moto (AWS mocking)
- pytest-cov (coverage)

**Test Cases Needed:**
1. Valid car data → successful write
2. Invalid car data → validation error logged
3. Missing required fields → clear error message
4. DynamoDB failure → proper error handling

## Exit Criteria

- [ ] All tests pass
- [ ] 100% code coverage
- [ ] README documents usage and deployment
- [ ] Error scenarios tested

## Files to Reference

- `docs/sums/TASK-CAR-INGESTION-P0-CORE.md` — What was built
- `src/models/car.py` — Model to test
- `src/handlers/car_ingestion.py` — Handler to test

---

## ⚠️ IMPORTANT — END OF PHASE

When this phase is complete, you MUST:

1. **Generate Summary** → `docs/sums/TASK-CAR-INGESTION-P1-TESTING.md`
2. **Update CLAUDE.md** → Mark task as complete
3. **Update README.md** → If needed

This is the final phase. No next prompt needed.

See `CLAUDE.md` for full protocol.
