# Planner

Started 2026-08-22. The pipeline is built and proven (see `LLM/2026-08-22 Handover, first TL curve.md`). What remains is understanding it. This note tracks the nine steps from a bare miniforge and a bare Jupyter to the TL curve, and how solid each one is.

## Status key

- **first pass**: a note exists but it came out of a chat session, LLM drafted. Readable, not yet trusted, not yet in John's words.
- **own words**: John has narrated it, corrections folded in, the note keeps his language.
- **solid**: own words plus checked against the live model or the element reference. Done.

## The nine steps

| Step | Component                                                                                                        | Status      | Note                                               |
| ---- | ---------------------------------------------------------------------------------------------------------------- | ----------- | -------------------------------------------------- |
| 1    | Two conda envs, kernel and frontend split by role                                                                | first pass  | [[1 - Environment set up|Environment set up]]                             |
| 2    | Repo layout: code repo, vault, scratch as run_location                                                           | first pass  | project CLAUDE.md, repo README                     |
| 3    | Solver lifecycle: separate process, attach or launch, two clients on 50052                                       | first pass  | [[3 - Solver at start|Solver at start]]                                |
| 4    | Viewer stack: trame native mode, ratios, cell data on the grid                                                   | own words   | [[4 - Interactive viewer|Interactive viewer]]                             |
| 5    | Model definition: parameters, element types, materials, geometry, naming by component, attributes                            | own words   | [[5 - Model definition|Model definition]], [[Model overview]], [[Geometry]], `double_wall.py` |
| 6    | Mesh and coupling: mesh sizes, meshing, coupled layer by ESLN, where UX and UY live             | own words   | [[6 - Mesh and coupling|Mesh and coupling]] |
| 7    | BCs and flags: FSI, IMPD with MU, rim clamps, do nothing equals rigid, FLOW source                               | first pass, approved in chat | [[7 - Boundary conditions and flags|Boundary conditions and flags]] |
| 8    | Solve and extract: HARMIC FULL sweep, POST26, section averages, two mic decomposition, the wall's own reflection | not started | `tl_sweep.py`                                      |
| 9    | Verification layers: counts, pictures, physics overlay, mesh convergence, geometry sweep                                                           | not started |                                                    |

## Concept notes beside the steps

| Note | Status | Feeds |
|---|---|---|
| [[X - Servers|Servers]] | not started, headings only | step 3 |
| [[X - Visualization tools|Visualization tools]] | reference, written on request | step 4 |
| [[X - Dictionary|Dictionary]] | reference, written on request | step 5 |
| [[X - Mesh type|Mesh type]] | reference, written on request | step 6 |

## Order of attack

Steps 5 to 8 first, one note each, John narrating before anything is written. Steps 1 to 3 get a read through and an own words pass after, since the notes exist and the facts are settled. Step 4 and 9 last.

## This week

Supervisor presentation: a breakdown of the system as set up, the nine steps as the walk through, ending on the two study plots as the proof. Mesh convergence (done 2026-08-23, `LLM\mesh_convergence.py`) and the geometry sweep (`LLM\geometry_sweep.py`, edge width 2.5 and 10 mm, wall thickness 3 and 8 mm, ready to run) are part of the study, not side jobs.

## Parked for later, after the easy steps

- Step 3 deep dive, the solver lifecycle cells. Cells 1 to 5 are in the notebook (2026-08-22), tested on a side port, reviewed. Record: [[2026-08-22 Solver lifecycle cells, design record]] in LLM. Remaining: John's rewrite of note 3 over the four routes (route C is wrong as written, exit needs force=True), and the open items listed in the record.

## Side jobs, not blocking

- Modal analysis of the wet structure to identify the 1610 Hz pole zero pair, or park it.
- Accuracy passes: PLANE182 to conform with FLUID29, r weighted FLOW, mesh convergence.
- Compare the split dip pair (about 280 and 350 Hz) against the AMM vault piston on surround analytics.
- ANSYS documentation conversion, its own chat: the 1566 PyMAPDL command reference pages from HTML to markdown under `Resources\ANSYS documentation\`, so the Table of methods in note 5 (and later 6 to 8) can link each APDL name to a local page. Handover: [[2026-08-22 Handover, ANSYS documentation conversion]].
- Housekeeping: notebook filename leading space, the `[84, 89, 109]` aplot chatter, redundant jupyterlab in the pyansys env.

## Log

- 2026-08-22: planner created, nine steps listed, 1 to 3 marked first pass.
- 2026-08-22: step 4 narrated by John, Interactive viewer note rewritten in his words. Distribution question checked against package metadata and PyPI, answer folded into the note. Graphics extra contents verified from installed metadata.
- 2026-08-22: notes moved into Starter notes and numbered by step. Servers note stubbed with headings for John to narrate into. The LLM draft sits in LLM as 2026-08-22 Servers, LLM draft.
- 2026-08-22: step 3 discussion ballooned into the lifecycle cell design. Cells in the notebook, record in LLM, revisit parked until the easy steps are done. Step 5 next.
- 2026-08-22: note 5 has headline, set up, geometry, and a Table of methods section at the end. Documentation conversion handed over to a dedicated chat.
- 2026-08-22: step 5 narrated end to end, note 5 own words. Script refactored to one domain table (DW_DOMAINS) feeding the naming, attribute and mesh size loops.
- 2026-08-23: note 6 narrated (coupled layer, FSI flag merged into the conversion block in the script), own words. Note 7 written from the chat explanation John approved, table linked to the converted docs.
- 2026-08-23: mesh convergence study run, converged defaults into the script (wall and edge 0.83 mm), result in note 6. Geometry sweep built on the shared runner, not yet run. Supervisor presentation this week noted.
