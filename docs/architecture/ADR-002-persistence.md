# ADR-002: Local-only persistence (no backend)

**Status:** Accepted  
**Date:** 2026-10-06

## Context

30-day non-goals include accounts, push, and multi-device sync. Data preference is hybrid long-term, but auto-pull is seam/stub only in phase 1.

## Decision

- All tournament, pool, strip, bout, and DE status data lives **on-device only**.  
- Persistence: **SwiftData** (iOS 17+).  
- No login, no cloud, no network requirement for core flows.  
- Product copy must state “on this phone only.”

## Consequences

- Single source of truth = this install; uninstall/device loss loses data (acceptable for phase 1).  
- Builder must not introduce auth SDKs or remote APIs for MVP features.  
- Hybrid ingestion (FencingTime etc.) is deferred; see ADR-004 for seams.
