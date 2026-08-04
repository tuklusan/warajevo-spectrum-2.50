# Module Index

## `src/environment`

| Module | Role inferred from source/name |
|---|---|
| `WARAJEVO.PAS` | Program entry point (`ZXTOOLS`), Turbo Vision application, configuration and emulator launch |
| `TAPES.PAS` | Tape-file management and format conversion |
| `SNAPSHOT.PAS` | Snapshot loading, saving, inspection, and conversion |
| `START.PAS` | Startup/run configuration |
| `SETUP.PAS` | Emulator settings and dialogs |
| `SETSTATE.PAS` | Menu construction and conversion commands |
| `IORUTINE.PAS` | File I/O support |
| `MICROD.PAS` | Microdrive image handling |
| `TIMEX.PAS` | Timex-specific environment support |
| `KONVTAP.PAS` | Tape conversion |
| `DBASE.PAS` | Software database management and launch records |
| `DOSMENU.PAS` / `MENUCONS.PAS` | Turbo Vision menu definitions |
| `HELPFILE.PAS`, `HELPCTX.PAS`, `HELP.TXT` | Help system |
| `HEXEDITO.PAS`, `EDITORS.PAS` | Editing facilities |
| `EXECZIP.PAS` | External archive/tool execution support |
| `ENDPROGR.PAS` | Program shutdown support |
| `CHAIN.PAS`, `CHAIN.OBJ` | DOS process chaining; third-party TurboPower code |
| `TVGRAPH.PAS`, `DETECT.PAS`, `FNT.PAS` | Graphics-mode Turbo Vision adaptation |
| `GADGETS.PAS`, `OPNDLG.PAS` | Turbo Vision support/demo-derived units |
| `READTAPE.ASM/.OBJ` | Low-level tape input support |
| `ENVCELO.ASM/.OBJ` | Assembly support for the environment |
| `PASUNRL.ASM/.OBJ` | 386 unreal-mode setup called by `SetUnReal` |
| `TPPATCH.EXE` | Historical runtime patch utility |
| `COMM.OBJ`, `COMM128.BZX`, other `.OBJ` | Prebuilt historical components required by old build paths |

## `src/spectrum-kernel`

| Module | Role |
|---|---|
| `SPECSIM.ASM` | Main 48K/128K emulator host, state and orchestration |
| `Z80.ASM` | Z80 instruction interpreter/emulation core |
| `TAPE.ASM` | Spectrum tape emulation and real-tape support |
| `SPECMON.ASM` | Machine-code monitor/debugger |
| `SPECLOGO.ASM` | Display/logo resources and routines |
| `ZXPRINT.ASM` | Printer emulation/output |
| `MDRIVE.ASM` | Microdrive emulation |
| `READTAPE.ASM` | Tape-reading helper |
| `PARALELL.ASM` | Parallel-port support |
| `TAPE2TAP.ASM` | Third-party tape capture/conversion utility |
| `VERSION.ASM` | Build-time 48K/128K switch |
| `SETEXE.BAT` | Build-time executable-name selection |
| `WORK.BAT` | Interactive edit/build/link/run driver |
| `SELECT.EXE` | Historical menu helper; third-party packed binary |

## `src/timex-kernel`

| Module | Role |
|---|---|
| `TS2068.ASM` | Main Timex Sinclair 2068 emulator host |
| `TSZ80.ASM` | Timex-oriented Z80 emulation core |
| `TSTAPE.ASM` | Timex tape subsystem |
| `TSMON.ASM` | Timex monitor/debugger |
| `TSLOGO.ASM` | Timex display/logo |
| `TSPRINT.ASM` | Timex printer support |

## `src/zx-compiler`

| Module | Role |
|---|---|
| `ZXCOMP.PAS` | Compiler front end for producing runnable DOS executables from snapshots |
| `IMPCOMP.PAS` | Compression/import support |
| `SPECCOMP.ASM` | Runtime emulator body used by compiled output |
| `Z80_C.ASM` | Z80 core for compiled output |
| `TAPE_C.ASM` | Tape support for compiled output |
| `OBJ48.PAS`, `OBJ128.PAS` | Embedded/generated object data declarations |
| `CONVROM.PAS`, `CONVR128.PAS` | ROM conversion/generation helpers |
| `MAKEEXE.BAT` | Historical compiler build command |

## Confidence labels

The table uses three confidence levels implicitly:

- **Direct:** stated by program declarations, build scripts, `uses`, `include`,
  `public`, or `extrn`.
- **Strong inference:** obvious from module names and repeated references.
- **Unresolved:** exact ownership of every routine and every old object file.

---

Copyright © 2026 Supratim Sanyal, SANYALnet Labs.  
Licensed under CC-BY-4.0. See `NOTICE.md`.
