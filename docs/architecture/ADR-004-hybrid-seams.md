# ADR-004: Hybrid auto-pull — seams only (30-day)

**Status:** Accepted  
**Date:** 2026-10-06

## Context

Long-term data preference is hybrid (auto-pull schedule/strips/results when possible; parents fill gaps + live scores). Implementing FencingTime scrape/API in 30 days is explicitly out of scope and a scope-creep risk.

## Decision

- Define narrow **protocol/stub** boundaries for future ingestion (e.g. `ScheduleImporting`, `ResultImporting`) that return empty / unimplemented in phase 1.  
- **Do not** call network endpoints, scrape, or show empty states that wait on external pull.  
- Manual entry remains the only write path for 30-day.

## Consequences

- Builder can leave stub types unused or behind `#if false` / no-op implementations.  
- 90-day work can fill seams without rewriting the local domain model.  
- Design must not depend on “waiting for FencingTime” empty states.
