## 1. Blocking from one real scene (U2)

- **Type:** **film session** (runs the hosted agent on the film root; edits no
  repository). Rafael judges.
- **Depends on:** fountain-input/1 (one scene of the pilot film in Fountain)
- **Contract:**
  - In: one converted scene and a minimal **bible** written by hand with
    Rafael (location layout and dimensions, characters, two or three camera
    rules)
  - Requires: the hosted agent proposes a shot list plus blocking (positions,
    camera, lens per shot) for the scene, in plain structured text. No code,
    no Blender
  - Delivers: the proposal and the bible in `<film-root>/previz-test/`, and in
    this file only Rafael's verdict: are positions and cameras coherent and
    consistent across shots, and what was wrong, worst first
- **Pre-work:** —
- **Out of scope:** rendering, file formats for the specs (they come out of
  this test)
- **Tests:** —
