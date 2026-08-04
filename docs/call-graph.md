# High-Level Call and Process Graph

## Environment application

```text
program ZXTOOLS
  |
  +-- preinit
  |    +-- locate WARAJEVO.EXE
  |    +-- read WARAJEVO environment variable
  |    +-- initialize video choice and paths
  |
  +-- TMyApp.Init
  |    +-- TApplication.Init
  |    +-- RegisterHelpFile
  |    +-- create names/status window
  |
  +-- prerun
  |    +-- parse process arguments
  |    +-- initialize tape/snapshot/Microdrive/dock objects
  |    +-- select machine type
  |    +-- parse DEFAULT.CFG or SPECSIM.CFG
  |    +-- queue Turbo Vision commands
  |
  +-- TMyApp.Run
  |    +-- HandleEvent
  |    +-- menu command dispatch
  |    +-- database workflow
  |    +-- setup/conversion/media workflows
  |
  +-- TMyApp.Done
  |
  +-- optional Chain4(curemul, '/c')
```

## Environment-to-emulator launch

```text
User/menu/database record
  -> build `comopts`
  -> save `SPECSIM.CFG`
  -> parse/validate configuration
  -> choose `curemul`
  -> DOS chain/execute emulator
```

## Classic emulator build-time linkage

`WORK.BAT` links:

```text
SPECSIM
+ Z80
+ SPECLOGO
+ ZXPRINT
+ TAPE
+ MDRIVE
+ SPECMON
    -> SPECSIM.EXE
    -> renamed to SPEC48.EXE or SPEC128.EXE
```

## Runtime core relationships

The assembly headers show extensive `extrn` and `public` coupling. At a high
level:

```text
SPECSIM.ASM
  <-> Z80.ASM       CPU execution and machine state
  <-> TAPE.ASM      edge/tape load/save behavior
  <-> SPECMON.ASM   monitor, disassembly, inspection
  <-> MDRIVE.ASM    Microdrive media and ports
  <-> ZXPRINT.ASM   printer output
  <-> SPECLOGO.ASM  display assets
```

A precise routine-level graph should be generated later by parsing all `public`,
`extrn`, `call`, and far-call statements. The current document deliberately
does not pretend that a filename-level graph is a routine-level graph.
