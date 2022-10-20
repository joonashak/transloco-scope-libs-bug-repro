# TranslocoScopeLibsBugRepro

Reproduction of a bug in `transloco-scoped-libs`. The `--skip-gitignore` flag is not respected when running in watch mode.

## Steps to Reproduce

1. Make a change to `src/assets/en.json`.
2. Run `npm run transloco:extract-scoped-libs`. Observe that `.gitignore` is not changed while `test/en.vendor.json` is correctly updated.
3. Run `npm run transloco:extract-scoped-libs:watch` and leave it running.
4. Make a change to `src/assets/en.json`. Observe that `.gitignore` is updated even though the script include the `--skip-gitignore` flag.
