---
apdl: "POLY"
method: poly
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.poly
generated: 2026-08-22
tags: [mapdl-command]
---

# POLY

PyMAPDL: `mapdl.poly(**kwargs)`

Creates a polygonal area based on working plane coordinate pairs.

## Notes

Defines a polygonal area on the working plane. The area will be defined with NPT keypoints and NPT lines, where NPT (must be at least 3) is the number of coordinate pairs defined with the [[ptxy|PTXY]] command. See the [[rpoly|RPOLY]] and [[rpr4|RPR4]] commands for other ways to create polygons.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_POLY.html
