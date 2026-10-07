# Product decision log — Epee Fencing Toolkit

Dated product locks. Architecture ADRs live in `docs/architecture/`.

| Date | Decision | Choice | Notes |
|------|----------|--------|-------|
| 2026-10-06 | Artifact home | GitHub `docs/` on bmucklow/epee-fencing-toolkit | Source of truth for requirements/docs |
| 2026-10-06 | Platform (30-day) | Swift / iOS + TestFlight | Eng recommendation; Blaine locked |
| 2026-10-06 | Data / auth (30-day) | Local-only, no accounts, single-device, no backend | Install via TestFlight; data stays on phone |
| 2026-10-06 | Min iOS | 17 | SwiftData + `@Observable`; Eng recommendation |
| 2026-10-06 | Test device | iPhone available | Blaine |
| 2026-10-06 | Apple Developer | Blaine to create | Needed for TestFlight red-line; reminder set |
| 2026-10-06 | 30-day sequence | A → B → C; protect A+B | Eng + Design co-review |
| 2026-10-06 | UX home frame | Focused fencer (“my kid today”) | Design; not tournament-director IA |
| 2026-10-06 | DE in 30-day | Read-only status list | Not a bracket editor |
