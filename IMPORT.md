# Initial import procedure

1. Download the four source archives from the official Warajevo source page.
2. Place them unchanged in `upstream/`.
3. Calculate SHA-256 hashes and record them in `docs/UPSTREAM.md`.
4. Inspect all archives for:
   - `LICENSE`, `COPYING`, and README files;
   - licence statements in Pascal and assembly headers;
   - third-party source or binary components;
   - ROM images.
5. Extract into:
   - `Warajevo.zip` → `src/environment/`
   - `Specsim.zip` → `src/spectrum-kernel/`
   - `Timex.zip` → `src/timex-kernel/`
   - `Compiler.zip` → `src/zx-compiler/`
6. Remove no files during the archival import.
7. Create the first commit with message:

   `Import original Warajevo 2.50 source archives`

8. Add documentation or build changes only in later commits.
