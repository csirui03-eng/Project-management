---
apdl: "PTXY"
method: ptxy
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.ptxy
generated: 2026-08-22
tags: [mapdl-command]
---

# PTXY

PyMAPDL: `mapdl.ptxy(x1='', y1='', x2='', y2='', x3='', y3='', x4='', y4='', **kwargs)`

Defines coordinate pairs for use in polygons and prisms.

## Parameters

**x1**, **y1**, **x2**, **y2**, **x3**, **y3**, **x4**, **y4**: X and Y coordinate pairs on the working plane.

## Notes

Defines coordinate pairs for use in polygons and prisms ( [[poly|POLY]], [[rprism|RPRISM]] ). The coordinates must be in the Cartesian coordinate system. The coordinate pairs must be input in a continuous order. **PTXY** may be repeated (up to 100 pairs) until the required pairs have been defined. The pairs will be saved until either the [[poly|POLY]] or [[prism|PRISM]] command is entered. Use **PTXY**,STAT to list the saved coordinate pairs. Use **PTXY**,DELE to delete all the saved coordinate pairs. See the [[rpoly|RPOLY]], [[rprism|RPRISM]], and [[rpr4|RPR4]] commands for other ways to create polygons and prisms.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PTXY.html
