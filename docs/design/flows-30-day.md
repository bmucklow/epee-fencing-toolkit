# 30-day UX flow outline (A→B)

## Job story

Parent at venue → know where my kid is → see/enter bout score → check pool standings feel → (later) DE status. All data lives on this phone.

## Happy path

1. Launch → Empty: “Follow a fencer today”
2. Create: Kid name (required) → Event nickname defaults to “Today” (editable) → optional club → Save → Kid hub
3. Kid hub: next strip / bout state; primary CTA Enter score or Set strip; secondary My pool
4. Add pool context: from hub or pool → “Add poolmate” (name only) → row appears; tap strip cell to set
5. Pre-bout: hub shows strip + opponent (if known) + Not started
6. Live: Enter score → large scores → +/- or tap-set → Save → hub shows final or in-progress
7. Between bouts: update strip on pool row or hub; mark bout Done
8. Repeat 5–7 through pool

## Alternate / edge

- Wrong score: reopen bout from hub → edit-in-place → Save
- Unknown strip yet: hub shows “Strip ?” + Set strip; pool row blank strip OK
- Only know kid first: hub usable with zero poolmates; soft prompt to add who they fence
- Second event later: New event from hub menu; prior event stays on-device (no sync UX)
- Time squeeze / no C: hub never blocks on DE; DE entry point hidden or deferred

## Out of scope UX (do not design into A+B)

Auth, accounts, multi-device, push, FencingTime pull, teammates, full bracket editor, other pools, tournament-director grids.

## C (if time): DE status list

Read-only rows: round / seed / opponent / strip / win-loss. Entry from hub after pools. No tree editor.

## A11y bar (every screen)

Large type, high contrast, ≥44pt primary targets, thumb-zone primary actions, portrait-first, score lock option, status not by color alone.
