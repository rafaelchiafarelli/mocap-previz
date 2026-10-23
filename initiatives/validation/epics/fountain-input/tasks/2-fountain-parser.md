## 2. Fountain parser

- **Type:** code, in the repository decision 8 names.
- **Depends on:** fountain-input/1 (for a real input), decisions/1 (decision 4
  conventions), a `mocap-contracts` task for `script.harpia` (`Scene`,
  `Character`, `Element`)
- **Contract:**
  - In: one `.fountain` file (spec 1.1)
  - Requires: our own parser (Jouvence loses accented names, screenplain drops
    notes and synopses: exploration §3.2); PT-BR headings as decided in
    decision 4; scene number as the scene identity
  - Delivers: one `script.harpia` message set per scene under
    `<film-root>/build/scenes/sc-<n>.json`, each with a hash of the scene's
    text so a rewrite reprocesses only the scenes that changed
- **Pre-work:** the `mocap-contracts` task above, done and tagged
- **Out of scope:** the breakdown agent, writer lint, diffing across rewrites
  (U1, its own task later)
- **Tests:** `docs/exploration/script-to-previz/spikes/fountain/sample_ptbr.fountain`
  plus cases for accents, dual dialogue, notes, synopses, forced elements and
  an all-caps action line
