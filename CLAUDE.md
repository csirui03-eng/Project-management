# CLAUDE.md

## Context

Obsidian vault for John's machine-side working notes: Ansys/MAPDL concept notes, model documentation (e.g. `Ansys\Double wall standard\`), acoustics notes, and resource extracts (`Resources\Extracts\`). Notes here are read by a human in Obsidian.

Code never lives in this vault. PyMAPDL/FEM code lives in `D:\Pyansys projects` (own git repo, hand-committed; machine-generated work under `LLM\`, John's model scripts in their own folders). MAPDL's working directory is that repo's gitignored `scratch\` folder.

## The Jupyter parallel setup (2026-08-21)

FEM work runs as two clients of one live MAPDL gRPC server (127.0.0.1:50052):

- John drives a JupyterLab notebook (kernel "Python (PyAnsys)", env `pyansys`), launching MAPDL with `launch_mapdl(run_location=<repo>\scratch)`.
- Claude attaches to the same running server from scripts (`Mapdl(ip="127.0.0.1", port=50052)`) to audit live model state: component contents, entity counts, glue checks, mesh statistics.
- State questions (is the selection right, did the glue take) are answered by attaching and counting, not by asking John for screenshots. Visual questions still go through plots/screenshots.
- Selections and components are shared server state. After any probe, restore with `ALLSEL` and `CMSEL,ALL`, and say when state was touched.
- Claude cannot see the live notebook kernel; the `.ipynb` on disk shows only its last save. To run something in John's session, hand him the cell.

Geometry work follows the geometry-creation loop: plain words first (vault note), code, view, screenshot problem areas, iterate; when settled, prune the trail to pseudocode plus final component plots. Verify selections by counts as well as pictures.

### Environment prerequisites (settled 2026-08-21, after debugging them one by one)

- Env `pyansys` (kernel): ansys-mapdl-core[graphics] (plot calls hard-fail without the extra), ipywidgets, ipykernel < 7 (ipykernel 7 breaks trame's in-kernel server: "cannot enter context" asyncio errors).
- Env `jupyter` (frontend): jupyterlab, ipywidgets. trame-jupyter-extension is installed but its comm bridge never connected; not relied on. jupyter-collaboration (RTC, added 2026-08-22): the notebook document lives in the Jupyter server, John's browser state is always persisted and readable from disk, and Claude's file edits flow live into open tabs (verified both directions). No save-then-reload dance for the notebook; avoid editing the same cell at the same moment.
- Interactive plots use pyvista's trame backend with NATIVE transport: set `os.environ["PYVISTA_TRAME_JUPYTER_MODE"] = "native"` BEFORE importing pyvista, then `pyvista.set_jupyter_backend("trame")`. The trame server is a per-kernel singleton: the first plot locks the transport mode until kernel restart, so the env var must run in the first cell.
- A stray system Python 3.13 (AppData\Local\Programs) shadows some `jupyter` subcommands on PATH with a broken install; always target envs explicitly (`conda run -n ...` or full python.exe paths).
- Before touching a new frontend feature (widgets, extensions), check dependencies on BOTH sides of the frontend/kernel env split first. This list exists because that check was skipped once.

## Hard rules (whose notes are whose)

- Notes under `Ansys\` (Starter notes, Double wall standard, concept notes) are John's own words notes. Claude never fills them with drafted prose. "Start a note" means create the title and section headings and stop. After John narrates, corrections fold into his sentences with minimal edits, and a rewrite keeps his phrasing in the lead.
- Anything Claude drafts in full (explanations from a chat, comparison tables, summaries, handovers) goes in `LLM\` as a dated file, linked from John's note if useful. Never into his note.
- Planner for the understanding phase: `Ansys\Starter notes\0 Planner.md`. Status moves from not started to first pass to own words to solid only on John's narration, not on Claude's writing.

## Hard rules (writing)

- No AI lexicon: the furthermore/moreover/notwithstanding transitions, the delve/leverage/utilize/foster/underscore verbs, the robust/comprehensive/pivotal/seamless adjectives, and the significantly/extremely intensifiers are banned in all output, prose or note. Full lists in the no-ai-slop skill's `ai-writing-detection.md` (copied to `.claude/skills/no-ai-slop/`, source: AMM-management vault).
- No dash characters in vault notes and reports: no em dash, no en dash, no double hyphen. Replace each dash with the mark specific to its role. Semicolons rationed to nearly zero: fused clauses take full stops. (John's 2026-07-23 instruction, carried over 2026-08-21.)
- Engineering vocabulary where an engineering term exists.
- No hard line wraps in markdown output: paragraphs and list items run one per line, letting the editor soft-wrap.

## Git

- This vault auto-syncs (obsidian-git). Sessions never commit or push the vault.
- The code repo (`D:\Pyansys projects`) is hand-versioned: commits are fine when John asks or work completes; the remote is `github.com/csirui03-eng/mam-fem`.
