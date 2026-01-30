# Copilot Instructions

This project uses **spec-driven development**.

## Key Files

- `CLAUDE.md` — Entry point, current state, full protocol
- `docs/specs/` — Specifications (human writes)
- `docs/plans/` — Development plans (AI generates)
- `docs/prompts/` — Phase prompts (AI generates)
- `docs/sums/` — Phase summaries (AI generates)

## Current State

Check `CLAUDE.md` for active work and next prompt location.

## End of Phase Protocol

At the end of EVERY phase:

1. **Generate Summary** → `docs/sums/{TYPE}-{NAME}-P{X}-{PHASE}.md`
2. **Generate Next Prompt** → `docs/prompts/{TYPE}-{NAME}-P{X+1}-{PHASE}.md`
   - Must include context from the summary
3. **Update CLAUDE.md** — Current state table
4. **Update README.md** — If user-facing changes
5. **Do not hallucinate**

## Naming

| Prefix | Use |
|--------|-----|
| `PROJ-` | Full project |
| `FEAT-` | Feature |
| `TASK-` | Task |
| `FIX-` | Bug fix |

See `CLAUDE.md` for full details.
