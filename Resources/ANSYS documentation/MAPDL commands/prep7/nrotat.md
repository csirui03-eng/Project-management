---
apdl: "NROTAT"
method: nrotat
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nrotat
generated: 2026-08-22
tags: [mapdl-command]
---

# NROTAT

PyMAPDL: `mapdl.nrotat(node1='', node2='', ninc='', **kwargs)`

Rotates nodal coordinate systems into the active system.

## Parameters

**node1**, **node2**, **ninc**: Rotate nodes from `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL, `NODE2` and `NINC` are ignored and all selected nodes ( [[nsel|NSEL]] ) are rotated. If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

## Notes

Rotates nodal coordinate systems into the active coordinate system. Nodal coordinate systems may be automatically rotated into the active (global or local) coordinate system as follows: Rotations in Cartesian systems will have nodal x directions rotated parallel to the Cartesian X direction. Rotations in cylindrical, spherical or toroidal systems will have the nodal x directions rotated parallel to the R direction. Nodes at (or near) a zero radius location should not be rotated. Nodal coordinate directions may be displayed ( [[psymb|/PSYMB]] ). Nodal forces and constraints will also appear rotated when displayed if the nodal coordinate system is rotated.

When the nodal coordinate systems are defined, they remain parallel to the global Cartesian system unless subsequently rotated.

Previously specified rotations on the specified nodes are overridden.

See the [[nmodif|NMODIF]], [[nang|NANG]], and [[nora|NORA]] commands for other rotation options.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NROTAT.html
