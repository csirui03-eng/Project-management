---
apdl: "/GTHK"
method: gthk
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.graphs.Graphs.gthk
generated: 2026-08-22
tags: [mapdl-command]
---

# /GTHK

PyMAPDL: `mapdl.gthk(label='', thick='', **kwargs)`

Sets line thicknesses for graph lines.

## Parameters

**label**

Apply thicknesses as selected from the following labels:

- `AXIS` - Modify thickness of ordinate and abscissa axes on graph displays.
- `GRID` - Modify thickness of grid lines on graph displays.
- `CURVE` - Modify thickness of curve lines (when no area fill ( [[gropt|/GROPT]] )).

**thick**

Thickness ratio (whole numbers only, from -1 to 10):

- `-1` - Do not draw the curve, but show only the markers specified by [[gmarker|/GMARKER]].
- `0 or 1` - Thin lines.
- `2` - The default thickness.
- `3` - 1.5 times the default thickness.
- `etc.` - (up to 10)

## Notes

Sets line thicknesses for graph lines (in raster mode only). Use **/GTHK**,STAT to show settings.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GTHK.html
