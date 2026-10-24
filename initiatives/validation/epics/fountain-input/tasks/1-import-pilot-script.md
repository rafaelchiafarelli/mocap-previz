## 1. Pilot script in Fountain

- **Type:** **film session** (no code). The importer itself is
  `mocap-writer` initiative `pdf-import` (moved there 2026-10-24, D8).
- **Depends on:** `mocap-writer` `pdf-import/importer/1` done
- **Contract:**
  - In: the pilot film's script, its `.docx` exported to PDF
  - Requires: a layout profile for it written with the importer's `probe`;
    no unknown-indent stop left; nothing hand-edited in the output without
    recording it
  - Delivers: `<film-root>/script/script.fountain`
- **Pre-work:** —
- **Out of scope:** any change to the importer (gaps go back to `mocap-writer`
  as tasks)
- **Tests:** —
