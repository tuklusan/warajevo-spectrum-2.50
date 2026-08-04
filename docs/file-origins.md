# File Origins and Provenance

## Primary archive mapping

| Official archive | Extracted directory |
|---|---|
| `Warajevo.zip` | `src/environment/` |
| `Specsim.zip` | `src/spectrum-kernel/` |
| `Timex.zip` | `src/timex-kernel/` |
| `Compiler.zip` | `src/zx-compiler/` |

The repository preserves the untouched archives under `upstream/`.

## Archive hashes

| Archive | SHA-256 |
|---|---|
| `Warajevo.zip` | `752BE812184AB4AD6EDB1367FA15ED14B53CF0AB36086BD833DC7271097657A2` |
| `Specsim.zip` | `20034F9F8F8A38E5B73160D8E7DF4863282CD93F8882658CC1B20AFE3B5F39DD` |
| `Timex.zip` | `EF9EEE5719619BF8892C0D7E3006D1C322358748E1BF11604D08F67F525A5313` |
| `Compiler.zip` | `720FE2E01831092B437A41DD79AB354B4AFBAAA5C9362FB8BDF342A538E50E6B` |

## Verified extraction counts

| Archive | Entries |
|---|---:|
| `Warajevo.zip` | 47 |
| `Specsim.zip` | 14 |
| `Timex.zip` | 6 |
| `Compiler.zip` | 10 |

The extraction was checked by comparing archive filenames with extracted
filenames and by matching entry counts.

## Historical timestamps

The ZIP archives retain DOS-era file timestamps. They are therefore primary
artifacts and should remain immutable.

## Preservation rule

- `upstream/`: untouched archives;
- `src/`: verbatim extraction;
- new code: place outside `src/`, or make changes on a clearly identified
  development branch while preserving the archival commit.

---

Copyright © 2026 Supratim Sanyal, SANYALnet Labs.  
Licensed under CC-BY-4.0. See `NOTICE.md`.
