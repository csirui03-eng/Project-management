---
apdl: "N"
method: n
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.n
generated: 2026-08-22
tags: [mapdl-command]
---

# N

PyMAPDL: `mapdl.n(node='', x='', y='', z='', thxy='', thyz='', thzx='', **kwargs)`

Defines a node.

## Parameters

**node**: Node number to be assigned. A previously defined node of the same number will be redefined. Defaults to the maximum node number used +1.

**x**, **y**, **z**: Node location in the active coordinate system (R, θ, Z for cylindrical, R, θ, Φ for spherical or toroidal). If `X` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**thxy**: First rotation about nodal Z (positive X toward Y).

**thyz**: Second rotation about nodal X (positive Y toward Z).

**thzx**: Third rotation about nodal Y (positive Z toward X).

## Returns

`int`: Node number of the generated node.

## Notes

Defines a node in the active coordinate system ( [[csys|CSYS]] ). The nodal coordinate system is parallel to the global Cartesian system unless rotated. Rotation angles are in degrees and redefine any previous rotation angles. See the [[nmodif|NMODIF]], [[nang|NANG]], [[nrotat|NROTAT]], and [[nora|NORA]] commands for other rotation options.

## Examples

Create a node at `(0, 1, 1)`

``` python
>>> nnum = mapdl.n("", 0, 1, 1)
>>> nnum
1
```

Create a node at `(4, 5, 1)` with a node ID of 10

``` python
>>> nnum = mapdl.n(10, 4, 5, 1)
>>> nnum
10
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_N.html
