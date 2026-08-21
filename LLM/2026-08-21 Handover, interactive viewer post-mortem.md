# Handover: interactive viewer post-mortem and double wall state

Next session opens with a discussion of what went wrong getting interactive 3D plots working in JupyterLab, and what the clean requirement list turned out to be. This note is the evidence base for that discussion. Written 2026-08-21.

## The failure chain, in order

1. First plot call failed outright: `aplot` raises ModuleNotFoundError in PyMAPDL 0.74 unless the optional graphics extra is installed. Fix: `pip install "ansys-mapdl-core[graphics]"` into env `pyansys`.
2. Plots rendered but only as static images. Cause: `pyvista.set_jupyter_backend("trame")` was configuring a library the plotter never consults in newer PyMAPDL, which routes through ansys tools visualization interface. A detour through that library's `USE_TRAME` flag was a dead end: it builds a standalone trame web application for a separate browser tab, not a notebook widget.
3. The real inline route (pyvista's trame backend) was silently degrading to static because ipywidgets was missing. Missing twice: once in the frontend env (`jupyter`, where JupyterLab runs) and once in the kernel env (`pyansys`). The setup splits frontend and kernel across two conda envs, and widget support must exist on both sides. Pyvista degrades without an error you would notice; the tqdm IProgress warning at launch was the same gap showing through.
4. ipykernel 7 broke trame's in kernel server with repeated asyncio errors ("cannot enter context: already entered"). Fix: pin `ipykernel<7` in env `pyansys`.
5. Extension mode (trame jupyter extension, the officially preferred transport) never worked: its static pages served fine (verified HTTP 200 against the running server) but the live channel between the lab extension and the kernel never connected. The widget sat on a perpetual loading spinner. Cause not found; the mode was abandoned rather than solved.
6. A test of native mode appeared to fail with an iframe pointing at `http://localhost:0` (port 0, dead page). This was a false negative: the trame server is a singleton per kernel, and the first plot of the session had already started it in extension mode. Mode switches after the first plot change the iframe URL but not the running server. Native mode had never been tested clean.
7. Fresh kernel, transport mode set before pyvista import: works. This is the resolution.

## The clean requirement list

- Env `pyansys` (kernel): ansys-mapdl-core[graphics], ipywidgets, ipykernel below 7.
- Env `jupyter` (frontend): jupyterlab, ipywidgets.
- First cell of any notebook, before importing pyvista: `os.environ["PYVISTA_TRAME_JUPYTER_MODE"] = "native"`, then `pyvista.set_jupyter_backend("trame")`.
- The transport mode is locked by the first plot of the kernel session. Changing it requires a kernel restart.
- These are recorded in `D:\Projects\CLAUDE.md` under Environment prerequisites, and live in cell 1 of the working notebook.

## Process lessons (John's critique, accepted)

- The environment should have been audited as a whole before starting notebook work: every widget feature needs its dependencies checked on both sides of the frontend and kernel env split.
- Guessing from memory cost several round trips. What worked: reading the installed source in site packages (that is where USE_TRAME, the port 0 singleton, and the TRAME_JUPYTER_WWW detection were all found), asking the live process (`etlist`, `cmlist`, attaching a second client to the MAPDL server), and testing components standalone (the trame server binds fine outside Jupyter, which isolated the fault to the kernel context).
- A stray system Python 3.13 in AppData shadows some `jupyter` subcommands on PATH with a broken install. Always target envs explicitly.

## Open loose end

- Every `aplot` in the double wall session prints `[84, 89, 109]`. Unexplained. Model state was verified clean by direct interrogation (areas 8 to 14, each component holds exactly one area), so it is cosmetic chatter from the plotting layer, but it has not been traced.

## State of the actual work (double wall model)

- `D:\Pyansys projects\Double wall test script\double_wall.py`: engineering data (PLANE183 axisymmetric, two FLUID29 variants, MDF, Shore 30A silicone, air), geometry (seven rectangles, AGLUE), selection and naming (seven area components, verified by counts from John's own kernel and by a second client attached to the live server).
- Notebook `run_double_wall.ipynb` (filename carries a leading space, still unrenamed): four cells, launch, `%run -i` build, viewer, component check.
- Next steps, in order: split the upstream air rectangle at y = ys so the source line exists as a mesh line (30 to 50 mm above the inlet, consider stretching l_up), attributes and mesh per component, line components (EXCITE_L, RADIATE_L, CLAMP_L, FSI faces), then loads. Before writing any FLUID29 flag: verify keyopt numbering, the IMPD absorber recipe, and the FLOW mass source syntax against the element's manual page, not memory.
- Boundary plan and measurement scheme (interior source line, anechoic both ends, two upstream mics, one downstream) are in `D:\Projects\Ansys\Double wall standard\Model overview.md`.

## Standing arrangements (unchanged, in CLAUDE.md)

- Two clients, one MAPDL server (port 50052): John in the notebook, Claude attaching for state audits, ALLSEL after every probe.
- Vault notes are the workshop copy; the module docstring is the condensed backup, updated before closing.
- Geometry creation loop: plain words, code, view, screenshot fixes, prune to pseudocode plus component plots when settled.
