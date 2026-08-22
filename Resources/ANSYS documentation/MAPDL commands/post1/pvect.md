---
apdl: "PVECT"
method: pvect
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.pvect
generated: 2026-08-22
tags: [mapdl-command]
---

# PVECT

PyMAPDL: `mapdl.pvect(oper='', labxr='', labyr='', labzr='', **kwargs)`

Interpolates a set of items onto a path.

## Parameters

**oper**

Valid operations for geometry operations along a path are:

- `NORM` - Defines a unit normal vector at each interpolation point in the direction of the cross product of the tangent to the path and the active Z axis. Resulting vector components are in the active coordinate system (which must be Cartesian).
- `TANG` - Defines a unit vector tangent to the path at each interpolation point. Vector components are in the active coordinate system (which must be Cartesian).
- `RADI` - Defines the position vector of each interpolation point of the path from the center of the active coordinate system (which must be Cartesian).

**labxr**: Label (8 characters maximum) assigned to X-component of the resulting vector.

**labyr**: Label (8 characters maximum) assigned to Y-component of the resulting vector.

**labzr**: Label (8 characters maximum) assigned to Z-component of the resulting vector.

## Notes

Defines and interpolates a set of labeled path items along predefined path ( [[path|PATH]] ) and performs various geometric operations on these path items. A path item must be defined before it can be used with other path operations. Additional path items may be defined with the [[pdef|PDEF]], [[pcalc|PCALC]], [[pdot|PDOT]], and [[pcross|PCROSS]] commands. Path items may be listed or displayed with the [[plpath|PLPATH]], [[plpagm|PLPAGM]] and [[prpath|PRPATH]] commands. Path geometry items (XG, YG, ZG, S) are automatically interpolated (in the active CSYS) if not done so previously with the [[pdef|PDEF]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PVECT.html
