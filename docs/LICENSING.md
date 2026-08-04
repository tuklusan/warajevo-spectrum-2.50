# Licensing status

## Upstream licensing statement

The official Warajevo download page states:

> Since February 2006, Warajevo is Open Source, with GPL license.

The official revision history states that release 2.52 was identical to release
2.51, except that the licence was changed to GPL and the available source code
was published.

The official pages do not identify:

- the exact GNU GPL version;
- whether the grant is “version N only” or “version N or later”;
- whether every file in all four archives is covered identically.

## Source archives inspected

The following official archives were downloaded from the Warajevo website and
inspected before extraction into this repository:

| Archive | SHA-256 |
|---|---|
| `Warajevo.zip` | `752BE812184AB4AD6EDB1367FA15ED14B53CF0AB36086BD833DC7271097657A2` |
| `Specsim.zip` | `20034F9F8F8A38E5B73160D8E7DF4863282CD93F8882658CC1B20AFE3B5F39DD` |
| `Timex.zip` | `EF9EEE5719619BF8892C0D7E3006D1C322358748E1BF11604D08F67F525A5313` |
| `Compiler.zip` | `720FE2E01831092B437A41DD79AB354B4AFBAAA5C9362FB8BDF342A538E50E6B` |

None of the four archives contains an obvious `LICENSE`, `LICENCE`, `COPYING`,
or GNU GPL text file.

No explicit GPL grant or GPL version was found in the inspected source-file
headers or in `HELP.TXT`.

## Warajevo-authored code

The main emulator, Timex emulator, and compiler assembly sources consistently
identify the authors as:

- Zeljko Juric
- Samir Ribic

Examples include:

- `SPECSIM.ASM`
- `Z80.ASM`
- `TS2068.ASM`
- `TSZ80.ASM`
- `SPECCOMP.ASM`
- `TAPE_C.ASM`
- `Z80_C.ASM`

These files carry copyright notices for Zeljko Juric and Samir Ribic but do not
state a GPL version in their headers.

## Third-party material

The upstream archives include files with separate copyright notices or unclear
redistribution terms.

Known examples include:

| File | Notice or attribution |
|---|---|
| `CHAIN.PAS` | TurboPower Software, 1987; “All rights reserved” |
| `EDITORS.PAS` | Borland International, 1992 |
| `GADGETS.PAS` | Borland International, 1990 |
| `HELPFILE.PAS` | Borland International, 1990 |
| `OPNDLG.PAS` | Borland International, 1990 |
| `DETECT.PAS` | C. L. Burke; portions credited to Borland |
| `TVGRAPH.PAS` | Associated with C. L. Burke's TVGRAPH code |
| `TAPE2TAP.ASM` | Rui Fernando Ferreira Ribeiro, 1995 |
| `SELECT.EXE` | Contains PKLITE material credited to PKWARE Inc. |
| `TPPATCH.EXE` | Historical Borland-era binary utility |

The inspected files do not contain clear redistribution permissions sufficient
to treat every third-party component as unambiguously GPL-covered.

## ROM and media inspection

No obvious ZX Spectrum ROM images, tape images, snapshots, or files with
`.rom`, `.bin`, `.tap`, `.tzx`, `.sna`, or `.z80` extensions were found in the
four inspected source archives.

No files of exactly 16,384 or 32,768 bytes were found by the initial ROM-size
check.

This does not prove that no ROM-derived data exists in source form, but no
obvious bundled ROM image was detected.

## Repository policy

1. Preserve every original copyright, authorship, and licence notice.
2. Do not assign a specific GNU GPL version without stronger upstream evidence.
3. Do not apply one blanket licence statement to third-party files whose terms
   differ or remain unclear.
4. Preserve the untouched official ZIP archives and their recorded hashes.
5. Clearly separate archival upstream material from repository-authored work.
6. Do not redistribute ZX Spectrum ROM images unless their rights are separately
   established.
7. Document exclusions, replacements, or rewrites of third-party components.
8. Add new development work only under clearly stated licensing terms that are
   compatible with the upstream code being modified.

This document records the evidence found during repository preparation. It is
not legal advice.
