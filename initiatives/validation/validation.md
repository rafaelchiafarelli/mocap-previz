# validation — mocap-previz

**Status:** Planned — not started. Waits for the `face-audio` verdict in
`mocap-studio` (Rafael: the face test comes first).

**Goal:** answer what has to be true before any previz pipeline is built:
Rafael's open decisions, a real script in Fountain that our own parser reads,
and whether the hosted agent can produce coherent blocking and cameras from a
real scene (exploration §6, unknown U2).

**Scope:** decisions (manual), the docx → Fountain converter and the Fountain
parser (code, deterministic, no LLM), one blocking test (a film session, no
code). Findings and proposals:
`docs/exploration/script-to-previz/README.md`.

**Out of scope:** the orchestrator, the film bible format, the Blender adapter
and SVG writer as product code, dashboard thumbnails, approval-by-rule. They
are planned as their own initiatives after this gate.

**Initiative gate:** the decisions are recorded, one real scene goes
docx → Fountain → parser output, and Rafael has judged the U2 blocking test.
The next initiatives are then planned from that, per the `mocap-workflow` skill.

Epics and their order: `epics/README.md`.
