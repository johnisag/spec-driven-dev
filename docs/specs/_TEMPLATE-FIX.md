# Spec: FIX-[NAME]

> Bug fix specification

## Problem

[What's broken?]

## Expected Behavior

[What should happen?]

## Actual Behavior

[What's happening instead?]

## Steps to Reproduce

1. [Step 1]
2. [Step 2]

## Suspected Cause

[If you have an idea]

## Affected Files

- [File path]

---

## Generate

**AI, please:**

1. Generate `docs/plans/FIX-[NAME].md` with fix plan
2. Generate `docs/prompts/FIX-[NAME]-P0-FIX.md` for the fix

Then at the end of **each phase** (if multi-phase):

3. Generate `docs/sums/FIX-[NAME]-P{X}-{PHASE}.md` with phase summary
4. Generate `docs/prompts/FIX-[NAME]-P{X+1}-{PHASE}.md` for next phase (if needed)
5. Update `CLAUDE.md` current state table

Follow the protocol in `CLAUDE.md`.
