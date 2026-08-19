## The five routes

The older three-layer list, plus the two layers it left out (3 and 4).

1. **Workbench journaling** (project level). Automates the Project Schematic: creating systems, linking cells, updating, parameter sweeps. IronPython (Python 2.7 syntax), saved as `.wbjn`. Record it: File > Scripting > Record Journal, click around, stop, read what it wrote.
2. **Mechanical scripting** (model level). Automates inside Mechanical: selection, meshing, loads, named selections, result extraction. Automation tab > Scripting, console with autocomplete and a Record button. Same trick: do it manually, study the output.
3. **Command snippets** (the seam). Raw APDL objects placed in the Mechanical tree, injected into `ds.dat` at solve. The escape hatch for solver features Mechanical does not expose. Survives regeneration; the tree stays the source of truth.
4. **APDL native** (solver level). The solver's own scripting language: parameters, `*DO`, `*IF`, `*GET`, macros. A deck is a program. Harvest from `ds.dat`, from the classic GUI's `jobname.log`, or from the VM decks in [[Ansys VM v242]] extracts.
5. **PyAnsys** (modern route, replaces 1 and 2 outright). CPython from your own environment: PyMAPDL holds a live gRPC session with the solver, PyMechanical drives the Mechanical tree. NumPy, matplotlib, real IDE, git. Steeper setup, no GUI dependency.

## Which route for what

- Sweep whole systems or projects: journaling.
- Automate tree operations you already do by hand: Mechanical scripting.
- Reach solver features the tree lacks: snippets.
- Full pipeline, version controlled, no GUI: APDL decks driven by PyMAPDL.

## The learning path (from the older log, still sound)

1. Record a journal of one simple workflow (modal analysis of a plate), read it line by line.
2. Modify one thing (a dimension, a material), replay it.
3. Move to the Mechanical console for loads and result extraction.
4. Graduate to PyMAPDL/PyMechanical once doing parameter sweeps.

Session addition to the path: read the `ds.dat` of a solved model early. It is the flattened truth of everything the GUI did, and the fastest APDL lesson available.

## For the MAM work

Parametric sweeps over membrane tension and mass position: PyMAPDL driving the sweep from Python, results straight into NumPy and matplotlib. Target solver is MAPDL acoustics (modal and harmonic); the acoustics cases in the VM extracts are verified starting decks.

## Links

[[MAPDL]], [[The classic workbench]]
