---
apdl: "RPRISM"
method: rprism
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.rprism
generated: 2026-08-22
tags: [mapdl-command]
---

# RPRISM

PyMAPDL: `mapdl.rprism(z1='', z2='', nsides='', lside='', majrad='', minrad='', **kwargs)`

Creates a regular prism volume centered about the working plane origin.

## Parameters

**z1**, **z2**: Working plane Z coordinates of the prism.

**nsides**: Number of sides in the polygon defining the top and bottom faces of the prism. Must be greater than 2.

**lside**: Length of each side of the polygon defining the top and bottom faces of the prism.

**majrad**: Radius of the major (or circumscribed) circle of the polygon defining the top and bottom faces of the prism. Not used if `LSIDE` is input.

**minrad**: Radius of the minor (or inscribed circle) of the polygon defining the top and bottom faces of the prism. Not used if `LSIDE` or `MAJRAD` is input.

## Notes

Defines a regular prism volume centered about the working plane origin. The prism must have a spatial volume greater than zero. (that is, this volume primitive command cannot be used to create a degenerate volume as a means of creating an area.) The top and bottom faces are polygonal areas that are parallel to the working plane but neither face need be coplanar with (that is, "on") the working plane. The first keypoint defined for each face is at θ = 0°. See the [[rpr4|RPR4]] and [[prism|PRISM]] commands for other ways to create prisms.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RPRISM.html
