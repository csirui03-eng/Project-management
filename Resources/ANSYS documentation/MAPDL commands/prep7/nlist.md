---
apdl: "NLIST"
method: nlist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nlist
generated: 2026-08-22
tags: [mapdl-command]
---

# NLIST

PyMAPDL: `mapdl.nlist(node1='', node2='', ninc='', lcoord='', sort1='', sort2='', sort3='', kinternal='', **kwargs)`

Lists nodes.

## Parameters

**node1**, **node2**, **ninc**: List nodes from `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL (default), `NODE2` and `NINC` are ignored and all selected nodes ( [[nsel|NSEL]] ) are listed. If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

**lcoord**

Coordinate listing key:

- `(blank)` - List all nodal information
- `COORD` - Suppress all but the XYZ coordinates (shown to a higher degree of accuracy than when displayed with all information).

**sort1**: First item on which to sort. Valid item names are NODE, X, Y, Z, THXY, THYZ, THXZ

**sort2**, **sort3**: Second and third items on which to sort. Valid item names are the same as for `SORT1`.

**kinternal**

Internal nodes listing key:

- `(blank)` - List only external nodes.
- `INTERNAL` - List all nodes, including internal nodes.

## Notes

Lists nodes in the active display coordinate system ( [[dsys|DSYS]] ). Nodal coordinate rotation angles are also listed (relative to the global Cartesian coordinate system).

Node listing can be in a sorted order (ascending). `SORT2`, for example, will be carried out on nodes having equal values of `SORT1`.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NLIST.html
