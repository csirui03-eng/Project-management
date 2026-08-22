---
apdl: "LMESH"
method: lmesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.lmesh
generated: 2026-08-22
tags: [mapdl-command]
---

# LMESH

PyMAPDL: `mapdl.lmesh(nl1='', nl2='', ninc='', **kwargs)`

Generates nodes and line elements along lines.

## Parameters

**nl1**, **nl2**, **ninc**: Mesh lines from `NL1` to `NL2` (defaults to `NL1` ) in steps of `NINC` (defaults to 1). If `NL1` = ALL, `NL2` and `NINC` are ignored and all selected lines ( [[lsel|LSEL]] ) are meshed. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` and `NINC` are ignored).

## Notes

Generates nodes and line elements along lines. Missing nodes required for the generated elements are created and assigned the lowest available numbers.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LMESH.html
