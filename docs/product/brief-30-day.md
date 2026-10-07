# Epee Fencing Toolkit — Product brief (30-day)

**Status:** READY — all gates locked 2026-10-06  
**Owners:** Product (shape) · Engineering Lead (architecture) · Design (UX)  
**Coordinator:** Engagement Lead  
**Repo:** https://github.com/bmucklow/epee-fencing-toolkit

---

## Job

Parents follow kids at épée tournaments without FencingTime Live refresh hell — pools, strip assignments, DE cut/bracket, live bout scores (verify the ref). Optional teammate visibility is later.

**Home frame (Design):** “My kid today” — every screen answers: Where is my kid? What’s the score? What’s next? Not a tournament-director console.

---

## Outcomes

| Horizon | Outcome |
|--------|---------|
| **30-day** | Installable phone test build (TestFlight / ad hoc OK) with manual tournament entry + core follow-along |
| **90-day** | Working prototype: schedule/strips/DE, scores, teammates |
| **Data preference** | Hybrid — auto-pull when possible; parents fill gaps + live bout scores. **In 30-day:** auto-pull is seam/stub only, not implemented |

**Red (Engagement):** can’t get an installable build on a real phone, or blocked >1 week on anything material.

**Status home:** Slack `#epee-fencing-toolkit-status` — weekly pulse Mondays 9:00 AM ET

---

## 30-day scope

### In (sequence — protect A+B under time pressure)

| Step | Scope |
|------|--------|
| **A** | Tournament/event + focused fencer + pools/strips view-edit |
| **B** | Live bout score enter/view |
| **C** | Simplified DE — read-only status list (seed/opponent/strip/W-L), not a bracket editor |

### Out (explicit non-goals)

App Store submission · accounts/auth · push · multi-device sync · FencingTime scrape/auto-pull · teammates · full bracket editor · other pools / director grids

### Architecture stance (Eng Lead)

Local-only persistence, single-device, no backend for 30-day. Hybrid auto-pull stays interfaces/stubs.

### UX stance (Design) — A+B must-haves

- Focused-fencer hub as default home
- Minimal create: kid name required; event defaults to “Today”; optional club
- My pool only; edit-in-place; strip on row; pre-size ~6–7 empty rows; add-as-you-learn
- Only my-kid bout scores required; other pool scores optional
- Live bout ≤2 taps from hub; large +/- ; score lock against pocket bumps
- Clear “on this phone only” — no FencingTime-waiting empty states
- A11y: large type, high contrast (sun/glare), ≥44pt targets, thumb-zone, portrait-first, status not by color alone

---

## Design annex — happy path

1. Empty → “Follow a fencer today”
2. Create → Kid hub
3. Add poolmates / set strips as learned
4. Enter score (live bout) → back to hub
5. Between bouts: update strip / mark done
6. Optional C: DE status list from hub after pools

**Wireframes:** W1 Empty · W2 Create · W3 Kid hub · W4 My pool · W5 Add poolmate · W6 Set strip · W7 Live bout · W8 Bout done · W9 Soft empty pool · W10 (opt) DE list

See also `docs/design/` for the canonical UX annex.

---

## Kit routing

Engagement → **Product + Eng Lead + Design** (co-refine) → Builder → Quality → Release → Platform Ops

See `docs/product/decision-log.md` for locked gates and `docs/product/outcomes.md` for success criteria.
