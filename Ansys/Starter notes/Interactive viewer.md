# Interactive viewer

First written 2026-08-21 after the post mortem. Rewritten 2026-08-22 in my own words, corrections folded in. What it takes for interactive 3D plots in the notebook. The core of it is simple, three pieces plus one configuration cell.

## 1. The graphics extra

In the pyansys environment, install the MAPDL package with the graphics extra so the package supports plotting at all:

`pip install "ansys-mapdl-core[graphics]"`

Plain ansys-mapdl-core carries no plotting. Plot calls fail outright without the extra, they do not degrade. The extra pulls in ansys-tools-visualization-interface and matplotlib, and the visualization interface drags in the trame stack (trame, trame-vtk, trame-vuetify, websockets). pyvista itself is a base dependency and comes regardless.

## 2. Both sides need ipywidgets, and ipykernel stays below 7

The notebook and the kernel must talk to each other, so ipywidgets goes in both the jupyter env (frontend) and the pyansys env (kernel). The kernel sends widget state, the frontend renders it. Either side missing degrades silently to static images, no error. That silence is what cost the night of 2026-08-21.

Keep ipykernel below version 7 in the pyansys env. Version 7 breaks trame's in kernel server (asyncio "cannot enter context" errors).

## 3. Cell 0: native mode, then the trame backend

Set the OS environment variable for pyvista's trame mode in Jupyter to native, then set the Jupyter backend to trame:

```python
import os
os.environ["PYVISTA_TRAME_JUPYTER_MODE"] = "native"
import pyvista
pyvista.set_jupyter_backend("trame")
pyvista.global_theme.trame.interactive_ratio = 2
pyvista.global_theme.trame.still_ratio = 2
```

Order matters twice. The env var must be set before pyvista is imported, not merely before the first plot. And the first plot of the session locks the transport mode, so changing it needs a kernel restart. The two ratios are sharpness: trame renders at canvas size times the ratio, default 1, and 2 reads cleanly on the HD screen.

## Is there a distribution that does all this?

Checked 2026-08-22 against installed package metadata and PyPI. Three candidates, none complete.

- `ansys-mapdl-core[all]` is `[graphics]` plus `[jupyter]`: the visualization interface, matplotlib, ipywidgets, jupyterlab. One line for pieces 1 and the kernel half of 2. It also drops jupyterlab into the kernel env, which is where the redundant jupyterlab install most likely came from.
- The `pyansys` metapackage (2026.1.3) pins PyAnsys libraries to versions tested together against one Ansys release. `pyansys[mapdl-all]` gives mapdl-core 0.73.1, mapdl-reader 0.56.0, visualization-interface 0.13.3. Nothing about jupyter, widgets, ipykernel, or trame, and it would downgrade mapdl-core from 0.74.1.
- `pyvista[jupyter]` is the nearest notebook side bundle: ipywidgets, the trame stack with known bad versions excluded, jupyter-server-proxy, nest-asyncio2.

None of this is a fault in the packages. Most people run one env and do not care about separation, and for them `ansys-mapdl-core[all]` plus an `ipykernel<7` pin is the whole setup, jupyterlab in the same env included. The two env split is our choice, made for a lean restartable frontend, and the duplication it causes is the price of that choice.

What no list covers for our split: the ipykernel < 7 pin (ipykernel is not a declared dependency of any of them, nobody excludes 7 yet), the two env split (every extra installs into one env, the frontend needs its own ipywidgets and jupyterlab because we keep it separate), and cell 0 (configuration, not a package). The honest distribution for this setup is an `environment.yml` per env in the code repo with the pins written down.

## Related

The env and kernel model behind the two sided install: [[Environment set up]]. The full failure chain that produced this list: [[2026-08-21 Handover, interactive viewer post-mortem]]. trame-jupyter-extension is installed in the frontend env but its comm bridge never connected, so nothing relies on it.
