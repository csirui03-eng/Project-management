# Environment set up

Written 2026-08-21 from the 2026-08-20 setup discussion. My phrasing leads, the corrections are folded in where they landed. The interactive plot additions from 2026-08-21 close it out.

## One line version

New env per project, name it for the ecosystem not the first package, pip as needed, ipykernel once, file the card once, restart kernels to pick up changes.

## The three objects

Everything in this note falls out of three objects that all get called "the kernel" somewhere.

- The environment is the pantry. A folder of packages with its own python.exe. Restocking it is the only install action that exists.
- The kernel spec is the address card, the index I kept reaching for. A small JSON file in the user profile saying "pyansys lives at `miniforge3\envs\pyansys\python.exe`". Jupyter's picker menu lists these cards. Static, tiny, never runs anything.
- The kernel process is what starts when a card is picked: that env's own Python launched as a live process. It executes cells, holds variables, dies on restart kernel. A running interpreter, not an index.

Chain, one hop per sentence: the notebook file records a spec name. The spec points at an environment's Python. Picking it starts a process from that Python. That process runs the cells with that env's packages.

## What I did, with corrections

Open the miniconda prompt, create a new empty env, name it pyansys. Named for the ecosystem, not the first package (it started life as pymapdl and got renamed).

`pip install ansys-mapdl-core` into it. Correction one: nothing compiled arrived. The package is a plain Python client, the phrasebook and the telephone. The Fortran solver core was already on disk from the Student install and never moves. Correction two: this is one client, not the fleet. PyDPF, PyMechanical and the rest are each their own pip install when wanted.

`pip install ipykernel`. Needed because the new env doesn't have Jupyter ("oh, I do, cause this new env doesnt have jupyter. Bruh"). This installs the machinery that lets the env's Python speak Jupyter's messaging protocol. It files nothing yet.

`python -m ipykernel install --user --name pyansys --display-name "Python (PyAnsys)"`. This is the act that files the card. My "slave the env to the kernel" picture pointed backwards: the env is not enslaved to the kernel, the kernel is the env's ambassador inside Jupyter.

The rename breakage, recorded because it will happen again: conda rename is secretly clone and delete, so the env path changes and any card filed before the rename points at a folder that no longer exists. Fix: re-file from inside the renamed env, then `jupyter kernelspec remove` the stale name. `jupyter kernelspec list` shows every card and the path it points to, the whole system laid bare.

Order barely matters. The only genuinely ordered steps are env before anything, and ipykernel before the card can be filed.

## Day to day

Activate env, pip install, restart kernel, import. That is the whole loop.

Jupyter itself never restarts for package changes, it is just the frontend. The spec, the registration, the picker: none of it is involved again unless the env moves or gets renamed.

## What barebones missed: interactive plots (2026-08-21)

One frontend, many kernels held up, but widgets are the one case where the frontend is not a passive terminal. The kernel sends widget state and the frontend must render it, so every widget feature needs its dependencies checked on both sides of the env split.

- Env pyansys (kernel): `ansys-mapdl-core[graphics]`, ipywidgets, ipykernel below 7.
- Env jupyter (frontend): jupyterlab, ipywidgets.
- First cell, before importing pyvista: `os.environ["PYVISTA_TRAME_JUPYTER_MODE"] = "native"`, then `pyvista.set_jupyter_backend("trame")`.
- The first plot of a kernel session locks the transport mode. Changing it needs a kernel restart.

Full failure chain and why each item is there: [[2026-08-21 Handover, interactive viewer post-mortem]]. The same list lives in the repo CLAUDE.md under Environment prerequisites and in cell 1 of the working notebook.

One PATH trap: a stray system Python 3.13 in AppData shadows some jupyter subcommands with a broken install. Target envs explicitly, `conda run -n` or the full python.exe path.
