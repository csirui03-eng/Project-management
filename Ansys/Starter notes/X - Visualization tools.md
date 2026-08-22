# Visualization tools

Started 2026-08-22. What the buttons around an `aplot` are and where they come from. Reference note, written on request.

![[aplot toolbar 2026-08-22.png]]

## Two packages draw this

Two packages are involved, and each owns one toolbar.

- **PyVista's trame viewer** draws the top bar. It is the generic 3D viewer that every PyVista plot gets in a notebook with the trame backend. Nothing Ansys specific in it.
- **PyAnsys visualization interface** (`ansys-tools-visualization-interface`) draws the left column. PyMAPDL hands its plots to this package, which adds the Ansys flavoured widgets on top of the PyVista scene.

`aplot` itself only builds the scene: one polydata per area, tessellated by MAPDL into display facets (the `quality` argument sets how fine). Everything interactive is the two packages above.

## Top bar, PyVista trame

| Button | Does |
|---|---|
| ⋮ | show or hide the menu |
| expand arrows | reset camera, fit everything |
| axis arrows, four | perspective view, then look down X, Y, Z |
| grid | toggle edge visibility: the facet edges of the drawn surfaces, not the mesh |
| box | toggle bounding box |
| ruler | toggle the axis grid with tick labels, model units |
| axes | toggle the small triad |
| server or local | toggle rendering mode, server side or client side |
| double arrow | toggle parallel projection |
| PNG | save screenshot |
| download | export the scene as HTML |

## Left column, PyAnsys visualization interface

| Button | Does |
|---|---|
| cube | isometric view |
| -YZ, +YZ, -XZ, +XZ, -XY, +XY | look at the named plane from the named side. The model lives in XY, so ±XY is flat |
| X↑ Y↑ Z↑ and ↓ ↓ ↓ | pan the camera a step along each axis |
| ruler with triangle | measure: a two handle distance widget. Handles snap to the nearest vertex of the drawn geometry (VTK point picker), label is three significant figures in model units |
| scissors | mesh slider, a clipping plane dragged through the model |
| camera | screenshot to file |
| branch | tree menu, list the actors in the scene and show or hide each |
| ruler | axis ruler, X Y Z bounds labelled in metres |
| target | pick rotation centre, click a point and the orbit turns about it |
| box | parallel projection toggle |
| eye | hide the button column |
| sun | dark mode toggle |

## Documentation

- PyVista, trame Jupyter backend: https://docs.pyvista.org/ (Jupyter notebooks section). The tooltips are the button documentation, the source is `pyvista/trame/ui/vuetify3.py`.
- PyAnsys visualization interface: https://visualization-interface.tools.docs.pyansys.com/ (user guide, widgets). Source is `ansys/tools/visualization_interface/backends/pyvista/widgets/`.
- PyMAPDL plotting, the `aplot` side: offline copy in the repo at `docs\pymapdl-0.74.1\`, user guide, plotting.

Related: [[4 - Interactive viewer|Interactive viewer]] for what has to be installed for any of this to appear.
