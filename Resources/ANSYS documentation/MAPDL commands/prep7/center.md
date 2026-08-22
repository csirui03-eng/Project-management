---
apdl: "CENTER"
method: center
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.center
generated: 2026-08-22
tags: [mapdl-command]
---

# CENTER

PyMAPDL: `mapdl.center(node='', node1='', node2='', node3='', radius='', **kwargs)`

Defines a node at the center of curvature of 2 or 3 nodes.

## Parameters

**node**: Number to be assigned to the node generated at the center of curvature.

**node1**, **node2**, **node3**: Three nodes used to calculated the center of curvature, as described under `RADIUS`.

**radius**

Used to control the interpretation of `NODE1`, `NODE2` and `NODE3` :

- `0` - `NODE1`, `NODE2` and `NODE3` lie on a circular arc. The program will calculate the center of curvature (and radius) (default).
- `≠, 0` - `NODE1` and `NODE2` are the endpoints of an arc, and `RADIUS` is the radius of curvature. The program will locate the center of curvature on the `NODE3` side of the `NODE1` - `NODE2` line if `RADIUS` \> 0, and opposite to `NODE3` if `RADIUS` \< 0.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CENTER.html
