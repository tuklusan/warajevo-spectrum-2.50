# Warajevo 2.50 Architecture

## Scope and evidence

This map describes the archival source at Git commit `7ec5ea6`, imported from
the four official Warajevo source archives. It distinguishes facts visible in
the source from conclusions that still require a successful historical build.

## System shape

Warajevo is split into a DOS-hosted Turbo Vision environment and separate
native DOS emulator executables.

```text
WARAJEVO.EXE (Turbo Pascal/Delphi 1)
  |
  | writes/reads SPECSIM.CFG and command-line options
  | selects machine type and executable
  v
SPEC48.EXE / SPEC128.EXE / Timex executable
  |
  +-- host user interface and lifecycle       SPECSIM.ASM / TS2068.ASM
  +-- Z80 CPU emulation                       Z80.ASM / TSZ80.ASM
  +-- tape subsystem                          TAPE.ASM / TSTAPE.ASM
  +-- monitor/debugger                        SPECMON.ASM / TSMON.ASM
  +-- screen/logo                             SPECLOGO.ASM / TSLOGO.ASM
  +-- printer                                 ZXPRINT.ASM / TSPRINT.ASM
  +-- Microdrive                              MDRIVE.ASM
```

The environment program is declared as `program ZXTOOLS` in `WARAJEVO.PAS`.
Its `uses` list ties together the Turbo Vision application, tape and snapshot
management, setup, database, Microdrive, Timex, conversion, and launch logic.

## Environment lifecycle

`WARAJEVO.PAS` provides the top-level lifecycle:

1. `preinit`
   - resolves the executable directory;
   - reads the `WARAJEVO` environment variable;
   - selects text or graphics mode;
   - initializes emulator-media names and directories.
2. `TMyApp.Init`
   - initializes Turbo Vision;
   - registers help;
   - creates the names/status window and heap display.
3. `prerun`
   - parses command-line parameters;
   - recognizes `.Z80`, `.DCK`, `.TAP`, and `.MDR`;
   - initializes tape, snapshot, Microdrive, and dock-cartridge objects;
   - selects an emulator type from snapshot information;
   - reads `DEFAULT.CFG` or `SPECSIM.CFG`;
   - optionally queues emulator/start commands.
4. `MyApp.Run`
   - processes Turbo Vision events and dispatches menu commands.
5. `MyApp.Done`
   - tears down Turbo Vision, video, memory, and related services.
6. Optional chaining
   - the code can invoke `chain4(curemul, '/c')`.

## Control boundary

The environment and emulator core communicate mainly through:

- executable selection (`curemul`, `emulators[emultype]`);
- command-line options (`comopts`);
- `SPECSIM.CFG`;
- media files such as TAP, Z80, MDR, and DCK;
- DOS process chaining.

This is a process boundary, not an in-process emulator library interface.

## Machine variants

The classic Spectrum build uses one source set for 48K and 128K. `WORK.BAT`
rewrites `VERSION.ASM` and `SETEXE.BAT`:

- `VER_128 equ 0` and `SPEC48.EXE`;
- `VER_128 equ 1` and `SPEC128.EXE`.

The Timex source tree is parallel but separate.

## Important constraints

- The emulator cores are x86 assembly programs that emulate a Z80. They are not
  Z80 programs themselves.
- The source expects DOS, direct port access, BIOS/DOS interrupts, and period
  development tools.
- Third-party Pascal units and binary utilities have separate or unclear terms;
  see `LICENSING.md`.
- This architecture map does not claim a successful reproducible build yet.

---

Copyright © 2026 Supratim Sanyal, SANYALnet Labs.  
Licensed under CC-BY-4.0. See `NOTICE.md`.
