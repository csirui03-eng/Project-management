---
apdl: "NANG"
method: nang
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.nodes.Nodes.nang
generated: 2026-08-22
tags: [mapdl-command]
---

# NANG

PyMAPDL: `mapdl.nang(node='', x1='', x2='', x3='', y1='', y2='', y3='', z1='', z2='', z3='', **kwargs)`

Rotates a nodal coordinate system by direction cosines.

## Parameters

**node**: Rotate coordinate system of this node.

**x1**, **x2**, **x3**: Global X, Y, Z components of a unit vector in new nodal X direction.

**y1**, **y2**, **y3**: Global X, Y, Z components of a unit vector in new nodal Y direction.

**z1**, **z2**, **z3**: Global X, Y, Z components of a unit vector in new nodal Z direction.

## Notes

Rotates a nodal coordinate system to the orientation specified by the X, Y and Z direction cosines. Existing rotation specifications on the node are redefined. If only two of the three unit vectors are specified, the third is defined according to the right hand rule. It is the responsibility of the user to ensure that input direction cosines are orthogonal in a right-handed system.

See the [[nmodif|NMODIF]], [[nrotat|NROTAT]], and [[nora|NORA]] commands for other rotation options.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NANG.html
