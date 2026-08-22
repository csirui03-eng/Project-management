---
apdl: "DLIST"
method: dlist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_constraints.FeConstraints.dlist
generated: 2026-08-22
tags: [mapdl-command]
---

# DLIST

PyMAPDL: `mapdl.dlist(node1='', node2='', ninc='', **kwargs)`

Lists DOF constraints.

## Parameters

**node1**, **node2**, **ninc**: List constraints for nodes `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If ALL (default), `NODE2` and `NINC` are ignored and constraints for all selected nodes ( [[nsel|NSEL]] ) are listed. If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

## Notes

Listing applies to the selected nodes ( [[nsel|NSEL]] ) and the selected degree of freedom labels ( [[dofsel|DOFSEL]] ).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DLIST.html
