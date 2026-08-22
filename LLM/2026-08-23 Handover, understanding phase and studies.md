# Handover: understanding phase, studies, and the write up ahead

Written 2026-08-23, about 02:30, at the end of the session that ran from the first TL curve handover through the own words notes to the first two parametric studies. The next chat opens on the remaining notes and a write up of everything up to the TL plot, to be explained to a supervisor this week.

## Where things stand

The pipeline is built, proven, and now understood in John's words through step 7 of nine. Planner: `Ansys\Starter notes\0 - Planner.md`. Status at close:

| Step | Note | Status |
|---|---|---|
| 1 | `1 - Environment set up` | first pass (LLM drafted 2026-08-21, not yet narrated) |
| 2 | none, lives in project CLAUDE.md | first pass |
| 3 | `3 - Solver at start` | first pass, and wrong in one place: route C's `exit()` is ignored without `force=True`. Rewrite parked for after the easy steps. |
| 4 | `4 - Interactive viewer` | own words |
| 5 | `5 - Model definition` | own words, linked table of methods |
| 6 | `6 - Mesh and coupling` | own words, convergence study folded in, linked table |
| 7 | `7 - Boundary conditions and flags` | first pass, approved in chat (Claude's explanation John accepted), linked table |
| 8 | not started | solve and extract: `tl_sweep.py`, FLOW source, HARMIC FULL sweep, POST26, two mic decomposition, the wall's own reflection |
| 9 | not started | verification layers: counts, pictures, physics overlay, mesh convergence, geometry sweep |

Concept notes beside the steps, all in `Ansys\Starter notes\`: `X - Servers` (stub with John's one paragraph), `X - Visualization tools` (reference), `X - Dictionary` (reference), `X - Mesh type` (reference).

## The notebook (` run_double_wall.ipynb`, 14 cells)

Cells 1 to 5 are the lifecycle cells designed and tested on 2026-08-22 evening (record: `LLM\2026-08-22 Solver lifecycle cells, design record.md`): names and imports, server start, server termination with archive, client attach, optional resume. Cells 6 to 14 are the old pipeline cells renumbered: build, domain viewer, component check, setup audit, material map, etype map, BC map, TL sweep, TL plot. The component check (cell 8) was replaced in chat by a four line list of entities per component beside the numbered aplot; John ran it and pasted the screenshot into note 5. The FLOW line in cell 9 reads -1 until the sweep cell runs, known and accepted.

## The model script (`double_wall.py`), refactored tonight

- Four parameter tables at the top: `DW_GEOM`, `DW_MAT` (now carrying `mu=1.0` on air), `DW_MESH`, and `DW_DOMAINS`, a dict keyed by component name holding `(y band, x band, material, element type, mesh size)`. The names exist in one place. Naming, attributes and mesh sizes are three loops over `DW_DOMAINS.items()`.
- Two override hooks, one line each, no effect unless the name exists in the calling namespace: `DW_GEOM_OVERRIDE`, `DW_MESH_OVERRIDE`.
- Coupled layer and FSI flag merged into one block: the flag is applied right after `EMODIF` while the wall node selection is live.
- Mesh defaults moved to the converged level: wall and edge 0.83 mm (6 across, Langfeldt's rule), air 5 mm. 1858 elements, 47 s per sweep.
- Verified on the live server after every refactor: 8 areas, 25 lines, same component contents, `SOURCE_L` on line 3.

## The studies (repo `LLM\`, machine side, John has not read them yet and said so)

- `study.py`: the engine. One case = name plus geometry and mesh overrides. Own run folder under `scratch\runs\<name>\` with db, rst, npz. Census includes FSI and IMPD flag counts and D entries so pipeline robustness is in the table. Dip pair and 1600 Hz feature per case. Resume: a case with an npz is loaded, not solved again.
- `mesh_convergence.py`: four levels. Result: levels at 6 across agree with each other and with air halved at 5 Hz resolution; the first mesh (2 through the wall, 3 across the edge) was 10 Hz high on the lower dip and 25 Hz high on the 1600 Hz feature. Plot `LLM\mesh_convergence.png`, copied to vault Attachments and embedded in note 6.
- `geometry_sweep.py`: baseline, edge width 2.5 and 10 mm, wall thickness 3 and 8 mm, mesh per case from the 6 across rule. First run failed at wall 3 mm: the downstream mic at an absolute 200 mm had no node row within 0.2 mm once the wall thickness moved the downstream column. Fixed in `tl_sweep.py`: mics snap to the nearest node row and the decomposition uses the actual row heights. Rerun was in progress at handover time, resuming at wall 3 mm. Read `LLM\geometry_sweep.png` and the printed table when it lands. First three cases already showed the pipeline holding: FSI count equal to the coupled element count every time, IMPD constant at 40, D tracking rim node density.
- Geometry sweep result (landed 02:45; two plots, `LLM\geometry_sweep_edge.png` and `LLM\geometry_sweep_wall.png`, the combined one was too busy). Pipeline held on all five: IMPD 40 throughout, FSI equal to the coupled count except 1 and 9 corner elements short on edge 2.5 and wall 3 (converted by `esln` any node, no face with both nodes on the wall, idle DOFs, harmless). Physics: edge width is the spring, dip pair 280/345 at baseline, 425/470 at 2.5 mm (47 to 60 dB at 50 Hz), 165/255 at 10 mm (34 dB at 50 Hz). Wall thickness is the mass, median offset 8.3 dB below for 3 mm and 7.8 dB above for 8 mm against mass law 8.9 and 8.2. The sharp feature is a structural mode moving with both: 1600 baseline, 1130 (3 mm), 1780 (8 mm), 1890 (edge 2.5), 1525 plus a second at 840 (edge 10), the disc flexing on its ring, not a plate mode. Unexplained: the edge 2.5 mm curve sits 3 to 4 dB below baseline in the mass law region despite the larger disc. Look before trusting that case.
- Open item from the mic fix: with the edge ring at 0.83 mm the free mesher grades the air near the walls, so the 80 mm row has 5 nodes where the 60 mm row has 11. Section averages over uneven rows are a rough approximation. Clean fix is sampling the mic sections by interpolation. Not a blocker.

## Documentation

A dedicated chat converted the PyMAPDL command reference: 1475 pages under `Resources\ANSYS documentation\MAPDL commands\<group>\<method>.md`, with frontmatter, signature, parameters, notes, and the Ansys help URL. Tables in notes 5, 6, 7 link into it as `[[method|APDL]]`. Memory entry `mapdl-command-pages` names the regenerating script.

## Working rules settled tonight (all in project CLAUDE.md now)

- Notes under `Ansys\` are John's. "Start a note" means headings only. Drafted content for his notes is shown in chat first and written on his word. Claude's own material goes in `LLM\` dated.
- Text between tool calls is not shown to John in this interface. Anything he must read goes at the end of the turn.
- RTC handles disk edits to `.py` files as well as the notebook (verified tonight, the earlier ystore stall was a one off).
- The Student licence holds one seat. A side instance on another port starts but logs "maximum licensed number of demo users reached"; the nproc cap test was inconclusive for that reason.

## Next

1. Read the geometry sweep result with John: pipeline robustness from the counts, physics from the curves (edge width should move the dip pair and the low frequency rise, wall thickness the mass law level and the 1600 Hz feature).
2. Note 8, solve and extract, John narrating. The pieces: FLOW on `SOURCE_L` (amplitude cancels, the mesh line matters), `ANTYPE,HARMIC` with `HROPT,FULL` because the coupled matrices are unsymmetric, POST26 extraction per node, section averages, the two mic decomposition and why |B/A| is about 1 in the high TL band (the wall's own reflection).
3. The write up: everything from bare environment to the TL plot, explainable to a supervisor, with the two study plots as the closing proof. John asked not to focus on it yet, but it is this week's target. The planner's "This week" section and the nine step breakdown are the skeleton.
4. Parked: note 3 rewrite, notes 1 and 2 own words pass, the solver lifecycle record's open items, the 1610 Hz modal check, the tl_sweep output names ignoring RUN.

## Standing arrangements

Two clients, one server on 50052, `ALLSEL` and `CMSEL,ALL` after every probe, say when state was touched. The notebook is John's and his tab is live through RTC. The scripts in repo `LLM\` are Claude's until John has read them.
