---
apdl: "NDELE"
method: ndele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.ndele
generated: 2026-08-22
tags: [mapdl-command]
---

# NDELE

PyMAPDL: `mapdl.ndele(node1='', node2='', ninc='', **kwargs)`

Deletes nodes.

## Parameters

**node1**, **node2**, **ninc**: Delete nodes from `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL, `NODE2` and `NINC` are ignored and all selected nodes ( [[nsel|NSEL]] ) are deleted. If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1`.

## Notes

Deletes selected nodes that are not connected to elements. Nodes may also be redefined instead of deleted, if desired. Boundary conditions (displacements, forces, etc.) as well as any coupling or constraint equations containing the deleted nodes are also deleted.

This command is also valid in the [[slashmap|/MAP]] processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NDELE.html
