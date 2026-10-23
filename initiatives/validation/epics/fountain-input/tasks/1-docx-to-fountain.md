## 1. docx → Fountain converter

- **Type:** code, in the repository decision 8 names (this one unless it says
  `mocap-preprod`).
- **Depends on:** decisions/1 (decisions 4 and 8)
- **Contract:**
  - In: a `.docx` screenplay whose paragraph styles mark scene heading,
    character, dialogue, parenthetical, transition and action
  - Requires: deterministic mapping from styles to Fountain elements, **no
    LLM**; the style → element table is declared in a file, not guessed; an
    unknown style stops the conversion with its name
  - Delivers: a CLI `docx → .fountain` that writes into the film root, and
    the mapping file format
- **Pre-work:** a **neutral** `.docx` fixture with the same style names as the
  pilot film's script (style names only, no film text), small enough to commit.
  Finding the style names is a short film-session read of the pilot `.docx`
- **Out of scope:** converting the pilot script itself (a film session runs
  the CLI on the film root)
- **Tests:** fixture → expected `.fountain`; unknown style; accented
  character names
