# Spectrum Boxed Tape Preservation

## Scope

This directory records four cassette images associated with boxed Sinclair ZX
Spectrum systems:

- `spectrum-48k/HORIZONS.TAP`
  - Horizons: Software Starter Pack
  - Associated with the original ZX Spectrum 48K package

- `spectrum-plus/GUIDEENG.TAP`
  - ZX Spectrum+ User Guide Companion Cassette
  - Associated with the ZX Spectrum+ package

- `spectrum-128k/NEVEREND.TAP`
  - The NeverEnding Story 128
  - Associated with the ZX Spectrum 128K package

- `spectrum-128k/Daley Thompson's Supertest - 128k.tzx`
  - Daley Thompson's Supertest 128K
  - Associated with the ZX Spectrum 128K package

## Emulator compatibility

Warajevo 2.50 supports TAP files.

Warajevo 2.50 also supports TZX input and includes conversion from TZX to its
internal tape format. The archived source implements this through `DoTzx` in
`src/environment/KONVTAP.PAS`, startup handling in
`src/environment/START.PAS`, and corresponding menu and help entries.

## Local preservation

The cassette images and their downloaded ZIP archives are retained locally
but intentionally excluded from Git.

Only this documentation and `SHA256SUMS.txt` are intended for the public
repository.

## Reason for exclusion

The cassette software remains copyrighted.

Availability from an archival download site does not, by itself, establish
permission to republish the software in an independent public GitHub
repository. No third-party redistribution permission has been established for
these files.

## Provenance

The files were downloaded on 2026-08-04 from World of Spectrum Classic archive
downloads hosted at `worldofspectrum.net`.

Downloaded archive names:

- `Horizons.tap.zip`
- `ZXSpectrumPlusUserGuideCompanionCassette.tap.zip`
- `NeverEndingStoryThe128.tap.zip`
- `DaleyThompsonsSupertest128.tzx.zip`

The files were extracted without modification. Screenshots present in some
archives were not retained in the preservation set.

## Integrity

SHA-256 checksums for the four extracted cassette images are recorded in
`SHA256SUMS.txt`.

## Licence exclusions

The cassette images are not licensed under:

- the GPL statement associated with Warajevo;
- the `CC-BY-4.0` licence applied to repository-authored documentation;
- any licence attributed to Supratim Sanyal or SANYALnet Labs.

Copyright and all other rights in the cassette software remain with their
respective rights holders.
