---
apdl: "FLIST"
method: flist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_forces.FeForces.flist
generated: 2026-08-22
tags: [mapdl-command]
---

# FLIST

PyMAPDL: `mapdl.flist(node1='', node2='', ninc='', **kwargs)`

Lists force loads on the nodes.

## Parameters

**node1**, **node2**, **ninc**: List forces for nodes `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If ALL, list for all selected nodes ( [[nsel|NSEL]] ) and `NODE2` and `NINC` are ignored (default). If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1`.

## Notes

Listing applies to the selected nodes ( [[nsel|NSEL]] ) and the selected force labels ( [[dofsel|DOFSEL]] ).

> [!WARNING]
> A list containing a node number that is larger than the maximum defined node ( `NODE2` ), could deplete the system memory and produce unpredictable results.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FLIST.html
