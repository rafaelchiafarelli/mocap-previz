## 1. PDF → Fountain importer

- **Type:** code, in the repository decision 8 names (this one unless it says
  `mocap-preprod`).
- **Depends on:** decisions/1 (decisions 4 and 8); `pdfplumber` (MIT) in the
  repo's Dockerfile and lockfile (not PyMuPDF: AGPL)
- **Contract:**
  - In: a screenplay PDF with selectable text, in master-scene format,
    exported by Final Draft, Celtx, Word or Google Docs (the pilot film's
    `.docx` is exported to PDF and enters here too)
  - Requires: deterministic classification by each line's left indent (x
    position), **no LLM**; the indent → element table (scene heading, action,
    character, parenthetical, dialogue, transition) is a **layout profile**
    declared in a file, one per source program, chosen explicitly on the
    command line, never guessed; a line whose indent matches no range stops
    the import with its page and line; page furniture (page numbers,
    `(MORE)`, `(CONT'D)`, `CONTINUED`) is dropped by rules in the profile;
    scene numbers in the margin become Fountain `#n#`
  - Delivers: a CLI `pdf → .fountain` that writes into the film root; a
    `probe` subcommand that lists the indents found in a PDF with counts and
    sample lines, so a film session can write a profile; the layout profile
    format
- **Pre-work:** **neutral** PDF fixtures, one per source program, made by hand:
  the text of `docs/exploration/script-to-previz/spikes/fountain/sample_ptbr.fountain`
  typed into each program and exported to PDF (no film text), small enough to
  commit
- **Out of scope:** scanned PDFs / OCR; non-master-scene formats; writing the
  profiles for the film's own PDFs and importing them (a film session does that
  with `probe` and the CLI on the film root)
- **Tests:** each fixture → expected `.fountain`; unknown indent; accented
  character names; dual dialogue (side-by-side columns); page furniture
  dropped; a scene that continues across a page break
