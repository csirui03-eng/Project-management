# Interactive viewer

Written 2026-08-21. What it takes for interactive 3D plots in a notebook, boiled down after the post-mortem. The core issue is three fold, plus one line of configuration.

1. Install the MAPDL client with the graphics package: `pip install "ansys-mapdl-core[graphics]"`. Plain ansys-mapdl-core carries no plotting at all, plot calls fail outright without the extra.
2. Install the thing that actually lets Jupyter notebooks do interactive plots in general, the widgets machinery: ipywidgets. And have it in both the jupyter env and the pyansys env so the two sides can talk to each other. The kernel sends widget state, the frontend renders it. Either side missing degrades silently to static images, no error.
3. Keep ipykernel below version 7 in the pyansys env. Version 7 breaks trame's in kernel server (asyncio "cannot enter context" errors).

Not an install but required: the first cell of the notebook, before pyvista is imported, sets `os.environ["PYVISTA_TRAME_JUPYTER_MODE"] = "native"` and then `pyvista.set_jupyter_backend("trame")`. The first plot of the session locks the transport mode, so changing it needs a kernel restart.

The env and kernel model behind the two sided install: [[Environment set up]]. The full failure chain that produced this list: [[2026-08-21 Handover, interactive viewer post-mortem]].
