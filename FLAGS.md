# FLAGS — the open-issue list

<!-- Not a diary. One entry per issue, id F-NNN, never renumbered. The reviewer appends from PR Flags
in its integration commit; the coordinator moves closed entries to the Closed list at wave close
(one line each). Engine reverse-engineering notes belong in docs/, not here. -->

Entry format:
```
### F-NNN · YYYY-MM-DD · «area» · OPEN | HUMAN | CLOSED
What was observed · where (unit and line, PROJECT.md §7 numbering) · what would resolve it · pointer
```

## Needs a human
<!-- engine patches, binaries, in-game checks, anything that needs the disc or an emulator. Each
entry says exactly what the human does. HANDOFF.md → Blocked mirrors this list with pointers. -->

## Open
<!-- anything an agent could still act on: a suspected source typo to confirm, a reading to settle
when the other store is translated, a container approaching its threshold -->

## CHECK positive controls
<!-- One entry per kind of violation deliberately planted and caught by CHECK (tools/README.md rule 3).
A checker that has never failed has never been tested. -->

## Closed
<!-- id · date · how it closed · pointer to rulings.md or the commit -->
