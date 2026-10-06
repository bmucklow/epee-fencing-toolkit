# ADR-003: Domain model — focused fencer + today event

**Status:** Accepted  
**Date:** 2026-10-06

## Context

UX home frame is “My kid today,” not a tournament-director console. Manual entry burden is the main product risk.

## Decision

Primary entities (SwiftData):

| Entity | Role | Notes |
|--------|------|--------|
| **Fencer** | Focused kid | Display name required |
| **Event** | “Today” tournament/event | Nickname defaultable (“Today”); optional club |
| **PoolSlot** | Row in *my* pool | Name; optional strip; ~6–7 pre-sized empty rows |
| **Bout** | Live / completed bout | Scores; my-kid bouts required; others optional |
| **DEStatus** | Simplified DE row | seed, opponent, strip, W-L — **read model**, not a bracket graph |

UI root = Fencer + active Event (not Event-as-root with many fencers).

## Consequences

- No model for other pools, full DE brackets, or multi-kid director views in 30-day.  
- Edit-in-place on pool rows; strip is a field on `PoolSlot`, not a separate assignment board.  
- Sequence protect A+B: Fencer/Event/PoolSlot/Bout first; `DEStatus` is step C.
