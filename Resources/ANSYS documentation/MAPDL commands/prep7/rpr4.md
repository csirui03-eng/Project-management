---
apdl: "RPR4"
method: rpr4
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.rpr4
generated: 2026-08-22
tags: [mapdl-command]
---

# RPR4

PyMAPDL: `mapdl.rpr4(nsides='', xcenter='', ycenter='', radius='', theta='', depth='', **kwargs)`

Creates a regular polygonal area or prism volume anywhere on the working plane.

## Parameters

**nsides**: The number of sides in the polygon or prism face. Must be greater than 2.

**xcenter**, **ycenter**: Working plane X and Y coordinates of the center of the polygon or prism face.

**radius**: Distance (major radius) from the center to a vertex of the polygon or prism face (where the first keypoint is defined).

**theta**: Angle (in degrees) from the working plane X-axis to the vertex of the polygon or prism face where the first keypoint is defined. Used to orient the polygon or prism face. Defaults to zero.

**depth**: The perpendicular distance (either positive or negative based on the working plane Z direction) from the working plane representing the depth of the prism. If `DEPTH` = 0 (default), a polygonal area is created on the working plane.

## Notes

Defines a regular polygonal area anywhere on the working plane or prism volume with one face anywhere on the working plane. The top and bottom faces of the prism are polygonal areas. See the [[rpoly|RPOLY]], [[poly|POLY]], [[rprism|RPRISM]], and [[prism|PRISM]] commands for other ways to create polygons and prisms.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RPR4.html
