---
apdl: "/EDGE"
method: edge
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.edge
generated: 2026-08-22
tags: [mapdl-command]
---

# /EDGE

PyMAPDL: `mapdl.edge(wn='', key='', angle='', **kwargs)`

Displays only the common lines (“edges”) of an object.

**Command default:**

For element plots, display common lines between all adjacent element faces. For contour plots, display only the common lines between non-coplanar faces.

## Parameters

**wn**: Window number (or ALL) to which command applies. The default window is 1.

**key**

Edge key:

**Elements Plots**

- `0` - Display common lines between all adjacent element faces.
- `1` - Display only the common lines between non-coplanar faces (that is, show only the edges).

**Contour Plots**

- `0` - Display only the common lines between non-coplanar faces.
- `1` - Display common lines between all element faces.

**angle**: Largest angle between two faces for which the faces are considered to be coplanar (0° to 180°). Defaults to 45°. A smaller angle produces more edges, a larger angle produces fewer edges.

## Notes

The `ANGLE` field is used in PowerGraphics to determine geometric discontinuities. It is a tolerance measure for the differences between the normals of the surfaces being considered. Values within the tolerance are accepted as coplanar (geometrically continuous). In postprocessing displays, results are not averaged across discontinuous surfaces.

A surface can be displayed as an edge outline without interior detail. This is useful for both geometry and postprocessing displays. Element outlines are normally shown as solid lines for geometry and displacement displays. Lines common to adjacent "coplanar" element faces are removed from the display. Midside nodes of elements are ignored.

The [[shrink|/SHRINK]] option is ignored with the edge option.

**/EDGE** is not supported for [[plesol|PLESOL]] and [[eshape|/ESHAPE]] displays when in PowerGraphics mode ( [[graphics|/GRAPHICS]],POWER).

The **/EDGE** command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EDGE.html
