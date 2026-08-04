# Upstream provenance

Official project home:

`https://worldofspectrum.net/warajevo/`

Official source download page:

`https://worldofspectrum.net/warajevo/Download.html`

Official revision history:

`https://worldofspectrum.net/warajevo/Revision.html`

## Required source archives

| Archive | Intended destination | SHA-256 |
|---|---|---|
| `Warajevo.zip` | `src/environment/` | pending |
| `Specsim.zip` | `src/spectrum-kernel/` | pending |
| `Timex.zip` | `src/timex-kernel/` | pending |
| `Compiler.zip` | `src/zx-compiler/` | pending |

After downloading, calculate hashes before extraction:

```bash
sha256sum upstream/*.zip
```

Then extract each archive without modifying filenames or line endings.
Commit the untouched archives and extracted source in the same initial archival
commit, or use two consecutive commits: first the original archives, then the
verbatim extraction.
