# Planner

Started 2026-08-22. The pipeline is built and proven (see `LLM/2026-08-22 Handover, first TL curve.md`). What remains is understanding it. This note tracks the nine steps from a bare miniforge and a bare Jupyter to the TL curve, and how solid each one is.

## Status key

- **first pass**: a note exists but it came out of a chat session, LLM drafted. Readable, not yet trusted, not yet in John's words.
- **own words**: John has narrated it, corrections folded in, the note keeps his language.
- **solid**: own words plus checked against the live model or the element reference. Done.

## The nine steps

| Step | Component | Status | Note |
|---|---|---|---|
| 1 | Two conda envs, kernel and frontend split by role | first pass | [[Environment set up]] |
| 2 | Repo layout: code repo, vault, scratch as run_location | first pass | project CLAUDE.md, repo README |
| 3 | Solver lifecycle: separate process, attach or launch, two clients on 50052 | first pass | [[Solver at start]] |
| 4 | Viewer stack: trame native mode, ratios, cell data on the grid | not started | [[Interactive viewer]] |
| 5 | Model definition: parameters, element types, materials, geometry, naming by component | not started | [[Model overview]], [[Geometry]], `double_wall.py` |
| 6 | Mesh and coupling: attributes per component, mesh sizes, coupled layer by ESLN, where UX and UY live | not started | |
| 7 | BCs and flags: FSI, IMPD with MU, rim clamps, do nothing equals rigid, FLOW source | not started | |
| 8 | Solve and extract: HARMIC FULL sweep, POST26, section averages, two mic decomposition, the wall's own reflection | not started | `tl_sweep.py` |
| 9 | Verification layers: counts, pictures, physics overlay | not started | |

## Order of attack

Steps 5 to 8 first, one note each, John narrating before anything is written. Steps 1 to 3 get a read through and an own words pass after, since the notes exist and the facts are settled. Step 4 and 9 last.

## Side jobs, not blocking

- Modal analysis of the wet structure to identify the 1610 Hz pole zero pair, or park it.
- Accuracy passes: PLANE182 to conform with FLUID29, r weighted FLOW, mesh convergence.
- Compare the split dip pair (about 280 and 350 Hz) against the AMM vault piston on surround analytics.
- Housekeeping: notebook filename leading space, the `[84, 89, 109]` aplot chatter, redundant jupyterlab in the pyansys env.

## Log

- 2026-08-22: planner created, nine steps listed, 1 to 3 marked first pass.
