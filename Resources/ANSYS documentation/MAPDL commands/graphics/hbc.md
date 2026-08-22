---
apdl: "/HBC"
method: hbc
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.hbc
generated: 2026-08-22
tags: [mapdl-command]
---

# /HBC

PyMAPDL: `mapdl.hbc(wn='', key='', **kwargs)`

Determines how boundary condition symbols are displayed in a display window.

## Parameters

**wn**: Window reference number. This number can be any window numbered 1 to 5, or ALL (for all active windows). Default = 1.

**key**

Controls hidden-surface boundary condition display behavior:

ON, YES or 1 = Enable - Your boundary condition symbols are processed by the hidden-surface algorithm (for 2D graphics devices) and use an improved pressure-contour display (for 2D and 3D graphics devices).

OFF, NO or 0 (default) = Disable (default) - Your boundary condition symbols are not processed by the hidden-surface algorithm..

## Notes

With **/HBC**, `WN`,ON in effect, Mechanical APDL does not display symbols obscured by the model in the current view (that is, symbols inside of or behind the model are not drawn). This behavior lessens display clutter.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HBC.html
