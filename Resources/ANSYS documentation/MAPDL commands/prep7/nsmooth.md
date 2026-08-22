---
apdl: "NSMOOTH"
method: nsmooth
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nsmooth
generated: 2026-08-22
tags: [mapdl-command]
---

# NSMOOTH

PyMAPDL: `mapdl.nsmooth(npass='', **kwargs)`

Smooths selected nodes among selected elements.

## Parameters

**npass**: Number of smoothing passes. Defaults to 3.

## Notes

Repositions each selected node at the average position of its immediate neighbors on the selected elements. The node positions converge after some number of smoothing passes. For some initial conditions, `NPASS` may need to be much larger than 3. If the boundary of a mesh is to be undisturbed (usually desirable), the boundary nodes should be unselected before issuing **NSMOOTH**.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSMOOTH.html
