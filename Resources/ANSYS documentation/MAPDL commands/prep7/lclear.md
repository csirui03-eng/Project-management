---
apdl: "LCLEAR"
method: lclear
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.lclear
generated: 2026-08-22
tags: [mapdl-command]
---

# LCLEAR

PyMAPDL: `mapdl.lclear(nl1='', nl2='', ninc='', **kwargs)`

Deletes nodes and line elements associated with selected lines.

## Parameters

**nl1**, **nl2**, **ninc**: Delete mesh for lines `NL1` to `NL2` (defaults to `NL1` ) in steps of `NINC` (defaults to 1). If `NL1` = ALL, `NL2` and `NINC` are ignored and the mesh for all selected lines ( [[lsel|LSEL]] ) is deleted. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` and `NINC` are ignored).

## Notes

Deletes all nodes and line elements associated with selected lines (regardless of whether the nodes or elements are selected). Nodes shared by adjacent meshed lines and nodes associated with non-line elements will not be deleted. Attributes assigned as a result of [[latt|LATT]] are maintained. In the program's response to the command, if a line or keypoint is tallied as "cleared," it means either its node or element reference was deleted.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCLEAR.html
