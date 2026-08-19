## The project schematic

The Workbench project schematic is a GUI for organising. Almost like a folder, or suppose, a repo.

The repo reading is literal. On disk the project is `project.wbpj` plus a `project_files\` tree, one subdirectory per system and cell; `dp0\SYS\MECH\` is where the deck and results land.

## The system block

A system block is a subfolder in that folder.

The top of the block holds information that is relatively generic and cross platform compatible: Engineering Data (materials) and Geometry (CAD). Solver agnostic; the same two cells can feed a Fluent system or an MAPDL one.

Then it contains Model, Setup, Solution and Results. Solver specific from here down.

## The MAPDL mapping

Model, Setup, Solution, Results are a granular breakdown of the key aspects of [[MAPDL]]:

- Model + Setup: `/PREP7` and `/SOLU` territory. Mesh, materials on elements, boundary conditions, analysis options.
- Solution: the `SOLVE` command and its run.
- Results: `/POST1` (and `/POST26` for time histories).

Two corrections to keep the analogy honest. The split of preprocessing into Model and Setup is Workbench's choice, not MAPDL's. And the cells are Mechanical's checkpoints, not MAPDL's: the solver sees none of them, it receives one flat deck (`ds.dat`) at solve time.

## What the schematic buys

- Makes the use of everything more intuitive and less dependent on knowing code.
- Lets people visualise the sharing of data: the schematic is a live dataflow diagram, and cell to cell links share data between systems (a shared Model between a structural and an acoustics block, for vibro-acoustics).
- The underrated third thing: it is a build system. State tracked per cell, staleness flagged downstream when something upstream changes, only the needed parts re-run. The ticks and question marks are dependency bookkeeping. The Parameter Set adds sweeps with zero code.

Condensed: no-code access plus automatic dependency management.

`ds.dat` is the seam where the Workbench world ends and the APDL one begins. The flattening is one way; there is no road back from deck to tree.
