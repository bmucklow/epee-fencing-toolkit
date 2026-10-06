# Builder-ready package — Epee Fencing Toolkit (30-day)

**Status:** Ready for Engagement → Builder  
**Date:** 2026-10-06  
**Inputs:** Product brief (`../product/brief-30-day.md`) · Design W1–W10 · ADR-001…004  
**Owner after handoff:** Builder (implementation). Architecture stays on ADRs/review only.

---

## 1. Mission (red line)

Ship a **TestFlight (or ad hoc) install** on Blaine’s iPhone where a parent can manually set up “my kid today,” manage **my pool** + strips, and enter/view **live bout scores**. DE status list is step **C** (ship if time; do not block A+B).

**Blocked >1 week on anything material = escalate to Engagement.**

---

## 2. Locked constraints

| Item | Lock |
|------|------|
| Language / UI | Swift / SwiftUI |
| Min iOS | **17** |
| Distribution | TestFlight (ad hoc OK) |
| Persistence | SwiftData, on-device only |
| Auth / backend / push / sync | **None** |
| FencingTime / auto-pull | Stub seams only (ADR-004) |
| Apple Developer | Blaine creating account (needed for TestFlight) |

---

## 3. Build sequence (protect A+B)

### A — Foundation + follow setup
1. Xcode project in this repo (app code at repo root).
2. SwiftData models per ADR-003: `Fencer`, `Event`, `PoolSlot`, `Bout` (+ empty `DEStatus` ok).
3. Screens: **W1** Empty → **W2** Create → **W3** Kid hub → **W4** My pool → **W5** Add poolmate → **W6** Set strip.
4. Minimal create: kid name required; event nickname defaults to “Today”; optional club.
5. Pool: pre-size ~6–7 rows; edit-in-place; strip optional on row.

### B — Live scores
6. **W7** Live bout (≤2 taps from hub): large +/- ; score lock against pocket bumps.
7. **W8** Bout done → return to hub.
8. Only **my-kid** bout scores required; other poolmates’ scores optional.

### C — Simplified DE (stretch inside 30-day)
9. **W10** DE status list: seed / opponent / strip / W-L — **read/update fields only**, no bracket editor or graph.
10. Reachable from hub after pools; do not block TestFlight on polish here.

### Soft empty
- **W9** Soft empty pool — never “waiting on FencingTime.”

---

## 4. Screen inventory ↔ acceptance

| ID | Screen | Must satisfy |
|----|--------|----------------|
| W1 | Empty | CTA “Follow a fencer today”; on-this-phone framing |
| W2 | Create | Kid name required; event default “Today”; optional club |
| W3 | Kid hub | Answers: where / score / what’s next |
| W4 | My pool | My pool only; edit-in-place; ~6–7 rows |
| W5 | Add poolmate | Name-only add-as-you-learn |
| W6 | Set strip | Strip on pool row |
| W7 | Live bout | ≤2 taps from hub; large controls; lock against bumps |
| W8 | Bout done | Persists; returns to hub |
| W9 | Soft empty | No hybrid-dependent empty state |
| W10 | DE list (opt) | Read-only-style status fields; no bracket editor |

**A11y (all):** large type, high contrast (glare), ≥44pt targets, thumb-zone, portrait-first, status not by color alone.

---

## 5. Non-goals (do not build)

App Store submission · accounts/auth · push · multi-device sync · FencingTime scrape/API · teammates · full bracket editor · other pools / director grids · Android

---

## 6. Suggested module layout

```
App/
  EpeeApp.swift
  Persistence/ModelContainer+SwiftData.swift
Models/
  Fencer.swift · Event.swift · PoolSlot.swift · Bout.swift · DEStatus.swift
Features/
  OnboardingEmpty/ · CreateFencerEvent/ · KidHub/
  MyPool/ · LiveBout/ · DEStatusList/
Seams/   (no-op)
  ScheduleImporting.swift · ResultImporting.swift
```

---

## 7. Definition of done (30-day)

- [ ] Builds in Xcode; min deployment iOS 17  
- [ ] SwiftData survives app restart (same device)  
- [ ] Happy path W1→W8 works on device  
- [ ] Installable via TestFlight (or ad hoc) on Blaine’s iPhone  
- [ ] No auth, no network dependency for core path  
- [ ] W10 optional; if cut, note in Release notes for Engagement  

---

## 8. Handoff

Engagement Lead may route this package to **Builder**.  
Architecture available for review/ADR amendments; not for implementation.
