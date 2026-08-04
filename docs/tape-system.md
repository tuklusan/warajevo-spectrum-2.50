# Tape System

## Components

- Environment: `TAPES.PAS`, `KONVTAP.PAS`, `READTAPE.ASM/.OBJ`
- Classic core: `TAPE.ASM`, `READTAPE.ASM`
- Timex core: `TSTAPE.ASM`
- Compiler runtime: `TAPE_C.ASM`
- External utility: `TAPE2TAP.ASM`

## Environment role

The environment manages native Warajevo tape files and conversions to and from
several historical emulator formats. `WARAJEVO.PAS` initializes the tape object
and passes configuration through files and command options.

## Emulator-core role

The assembly tape modules integrate edge detection, loading/saving, host timing,
and real-tape or captured-tape behavior with CPU execution.

## Third-party utility

`TAPE2TAP.ASM` identifies Rui Fernando Ferreira Ribeiro as its author. It is a
separate DOS tape-reading utility and should not be silently treated as
Warajevo-authored code.

## Accuracy risks

Tape emulation is timing-sensitive. Future tests should cover:

- ROM loader compatibility;
- custom loaders;
- pulse widths and edge ordering;
- pause handling;
- checksum behavior;
- sound-card/parallel-port paths where applicable;
- host-speed independence.

---

Copyright © 2026 Supratim Sanyal, SANYALnet Labs.  
Licensed under CC-BY-4.0. See `NOTICE.md`.
