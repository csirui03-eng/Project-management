---
apdl: "KMESH"
method: kmesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.kmesh
generated: 2026-08-22
tags: [mapdl-command]
---

# KMESH

PyMAPDL: `mapdl.kmesh(np1='', np2='', ninc='', **kwargs)`

Generates nodes and point elements at keypoints.

## Parameters

**np1**, **np2**, **ninc**: Mesh keypoints from `NP1` to `NP2` (defaults to `NP1` ) in steps of `NINC` (defaults to 1). If `NP1` = ALL, `NP2` and `NINC` are ignored and all selected keypoints ( [[ksel|KSEL]] ) are meshed. If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NP1`.

## Notes

Missing nodes required for the generated elements are created and assigned the lowest available numbers.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KMESH.html
