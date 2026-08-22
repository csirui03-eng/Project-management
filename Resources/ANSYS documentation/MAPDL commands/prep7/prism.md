---
apdl: "PRISM"
method: prism
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.prism
generated: 2026-08-22
tags: [mapdl-command]
---

# PRISM

PyMAPDL: `mapdl.prism(z1='', z2='', **kwargs)`

Creates a prism volume based on working plane coordinate pairs.

## Parameters

**z1**, **z2**: Working plane Z coordinates of the top and bottom of the prism.

## Notes

Defines a prism volume based on the working plane. The top and bottom areas will each be defined with NPT keypoints and NPT lines, where NPT (must be at least 3) is the number of coordinate pairs defined with [[ptxy|PTXY]] command. Also, a line will be defined between each point pair on the top and bottom face. See the [[rprism|RPRISM]] and [[rpr4|RPR4]] commands for other ways to create prisms.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRISM.html
