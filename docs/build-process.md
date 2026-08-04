# Historical Build Process

## Environment executable

`src/environment/C.BAT` shows two historical compiler paths:

- a commented Turbo Pascal command;
- an active Delphi 1 command using `dcc`.

The active command compiles `warajevo` with Delphi 1's DOS compiler and then
calls `OVERLAY.BAT`. `OVERLAY.BAT` concatenates the overlay into the executable
and deletes the separate overlay file.

The environment source also contains Turbo Pascal overlay directives such as
`{$O TAPES}` and `{$O SNAPSHOT}`.

## Classic 48K/128K emulator

`src/spectrum-kernel/WORK.BAT` is an interactive build controller.

### Tools and assumptions

```text
Assembler: TASM, with one explicit MASM invocation for Z80.ASM
Linker:    TLINK
Editor:    external DOS editor
Menu:      SELECT.EXE
Host:      DOS with direct hardware access
```

### Variant selection

48K:

```text
VERSION.ASM: VER_128 equ 0
SETEXE.BAT:  SET EXE=SPEC48.EXE
```

128K:

```text
VERSION.ASM: VER_128 equ 1
SETEXE.BAT:  SET EXE=SPEC128.EXE
```

### Modules assembled and linked

```text
SPECSIM
Z80
SPECLOGO
ZXPRINT
TAPE
MDRIVE
SPECMON
```

The linker initially produces `SPECSIM.EXE`; the script renames it to the
selected variant.

## ZX compiler

`MAKEEXE.BAT` is the historical entry point, but a reproducible build still
requires inspection of its exact compiler/linker dependencies and generated
Pascal object-array units.

## Timex build

The source archive contains the Timex modules but no Timex-equivalent `WORK.BAT`.
The exact historical Timex link command is therefore unresolved from the
archive files inspected so far.

## Reproduction plan

A responsible reproduction should proceed in this order:

1. preserve the archival tree unchanged;
2. build a DOS toolchain VM/container separately;
3. record exact compiler, assembler, and linker versions;
4. attempt the original scripts without source edits;
5. capture logs and binary hashes;
6. compare behavior under DOSBox-X/86Box and real-compatible DOS assumptions;
7. modernize only on a separate branch/directory.

No modern build claim should be made until the historical build is demonstrated.
