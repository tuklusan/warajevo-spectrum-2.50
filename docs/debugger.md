# Monitor and Debugger

## Modules

- `SPECMON.ASM`: classic Spectrum monitor;
- `TSMON.ASM`: Timex monitor.

## Evidence

The build script links `SPECMON` into both classic machine executables. The
source contains mnemonic tables including Z80 I/O forms such as `OUT (C),0`,
which indicates disassembly/monitor support.

## Likely responsibilities

Based on naming, linkage, and symbol references:

- register and memory inspection;
- disassembly;
- machine-code monitor commands;
- interaction with the running emulator core;
- break/inspection facilities.

## Unresolved details

The archive has not yet been reduced to a command reference or routine-level
monitor architecture. In particular, the following remain to be documented:

- breakpoint model;
- single-step implementation;
- watchpoint support, if any;
- command syntax;
- how monitor entry affects emulated timing;
- whether monitor state is serialized.

These must be extracted directly from `SPECMON.ASM`, `TSMON.ASM`, and help text
before being stated as facts.
