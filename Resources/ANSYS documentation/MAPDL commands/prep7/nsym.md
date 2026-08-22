---
apdl: "NSYM"
method: nsym
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nsym
generated: 2026-08-22
tags: [mapdl-command]
---

# NSYM

PyMAPDL: `mapdl.nsym(ncomp='', inc='', node1='', node2='', ninc='', **kwargs)`

Generates a reflected set of nodes.

## Parameters

**ncomp**

Symmetry key:

- `X` - X (or R) symmetry (default).
- `Y` - Y (or θ) symmetry.
- `Z` - Z (or Φ) symmetry.

**inc**: Increment all nodes in the given pattern by `INC` to form the reflected node pattern.

**node1**, **node2**, **ninc**: Reflect nodes from pattern beginning with `NODE1` to `NODE2` (defaults to `NODE1` ) in steps of `NINC` (defaults to 1). If `NODE1` = ALL, `NODE2` and `NINC` are ignored and pattern is all selected nodes ( [[nsel|NSEL]] ). If `NODE1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NODE1` ( `NODE2` and `NINC` are ignored).

## Notes

Generates nodes from a given node pattern by a symmetry reflection. Reflection is done in the active coordinate system by changing a particular coordinate sign. Nodes in the pattern may have been generated in any coordinate system. Nodal rotation angles are not reflected.

Symmetry reflection may be used with any node pattern, in any coordinate system, as many times as desired. Reflection is accomplished by a coordinate sign change (in the active coordinate system). For example, an X-reflection in a Cartesian coordinate system generates additional nodes from a given pattern, with a node increment added to each node number, and an X coordinate sign change. An R-reflection in a cylindrical coordinate system gives a reflected "radial" location by changing the "equivalent" Cartesian (that is, the Cartesian system with the same origin as the active cylindrical system) X and Y coordinate signs. An R-reflection in a spherical coordinate system gives a reflected "radial" location by changing the equivalent Cartesian X, Y, and Z coordinate location signs. Nodal coordinate system rotation angles are not reflected.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NSYM.html
