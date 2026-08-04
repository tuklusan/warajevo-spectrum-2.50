# Z80 Emulation Core

## What it is

`Z80.ASM` and `TSZ80.ASM` are x86 assembly implementations of a Z80 CPU
interpreter. They run on the DOS host and emulate Spectrum/Timex Z80 state.

The source headers identify the Warajevo authors and expose many shared symbols
through `public` and `extrn` declarations.

## Responsibilities visible from headers and build linkage

- primary and alternate Z80 registers;
- index registers and interrupt registers;
- flags and interrupt mode/state;
- opcode dispatch;
- port input/output integration;
- timing and slow/fast execution paths;
- calls into tape edge detection, monitor, interrupt, and host timing services.

## Architecture style

The core appears to use x86 registers as cached representations of Z80
registers where practical. The compiler runtime uses a related but separate
core (`Z80_C.ASM`).

## Variants

- `Z80.ASM`: classic Spectrum 48K/128K emulator;
- `TSZ80.ASM`: Timex machine;
- `Z80_C.ASM`: snapshot compiler runtime.

These should not be casually deduplicated. Similarity does not prove identical
machine assumptions, timing, or linked services.

## Accuracy status

No percentage accuracy claim can be derived from the source archive. Accuracy
must be measured against test suites and hardware behavior, including:

- documented and undocumented opcodes;
- flags;
- interrupt timing;
- contention;
- I/O timing;
- floating bus and ULA behavior;
- tape edge timing;
- 48K/128K paging;
- Timex-specific behavior.

## Next analysis task

Generate a machine-readable symbol graph and opcode coverage table from all
three Z80 cores. That should be done by tooling, not by heroic eyeballing.

---

Copyright © 2026 Supratim Sanyal, SANYALnet Labs.  
Licensed under CC-BY-4.0. See `NOTICE.md`.
