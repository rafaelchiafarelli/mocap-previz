# mocap-previz

Script → shot list → **3D blocking in Blender** → **layered SVG storyboard**.
Part of the workhorse (pre-production → production) of
[Mocap Studio](https://github.com/rafaelchiafarelli/mocap-studio). No
AI-generated images: AI may only write the text (specs) that the 3D scene is
built from, and every output stays editable.

**Status (2026-10-23):** no code yet. Findings, two spikes and the proposed
architecture are in
[`docs/exploration/script-to-previz/`](docs/exploration/script-to-previz/README.md).
The first initiative, [`validation`](initiatives/validation/validation.md),
waits for the face test (`mocap-studio` initiative `face-audio`).

## Rules

- Python 3.12 (stack in `mocap-studio/DEPENDENCIES.md`); Blender 5.2.2. The
  Blender-coupled code (Line Art bake + reading stroke points) stays in one
  adapter module; everything else is pure Python.
- Talks to other repositories only through **`mocap-contracts`** messages
  (`.harpia`) and the film root layout. No code from another `mocap-*`
  repository is imported.
- Holds nothing film-specific: tests use neutral fixtures. Inputs and outputs
  live in the **film root**, never here.
- Planning and branches: the `mocap-workflow` skill in
  `.claude/skills/mocap-workflow/` and [`initiatives/`](initiatives/README.md).

## Layout

| Path | What |
|---|---|
| `docs/exploration/script-to-previz/` | exploration record and spikes (`lineart_svg_spike.py`, Fountain parser probes) |
| `initiatives/` | initiatives → epics → tasks |
| `third_party/mocap-contracts/` | submodule, pinned to `v0.3.0` (fixtures and `.harpia` sources; code comes from the pinned pip package once there is code) |

```bash
git clone --recurse-submodules git@github.com:rafaelchiafarelli/mocap-previz.git
```
