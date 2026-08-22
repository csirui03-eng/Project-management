---
apdl: "CSYS"
method: csys
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.coordinate_system.CoordinateSystem.csys
generated: 2026-08-22
tags: [mapdl-command]
---

# CSYS

PyMAPDL: `mapdl.csys(kcn='', **kwargs)`

Activates a previously defined coordinate system.

## Parameters

**kcn**

Specifies the active coordinate system, as follows:

- `0 (default)` - Cartesian
- `1` - Cylindrical with global Cartesian Z as the axis of rotation
- `2` - Spherical
- `4 or WP` - Working Plane
- `5` - Cylindrical with global Cartesian Y as the axis of rotation
- `6` - Cylindrical with global Cartesian X as the axis of rotation
- `11 or greater` - Any previously defined local coordinate system

## Notes

The **CSYS** command activates a previously defined coordinate system for geometry input and generation. The [[local|LOCAL]], [[clocal|CLOCAL]], [[cs|CS]], [[cskp|CSKP]], and [[cswpla|CSWPLA]] commands also activate coordinate systems as they are defined. To set the active element coordinate system attribute pointer, issue the [[esys|ESYS]] command.

The active coordinate system for files created via the [[cdwrite|CDWRITE]] command is Cartesian ( **CSYS**,0).

This command is valid in any processor.

**CSYS**,4 (or **CSYS**,WP) activates working plane tracking, which updates the coordinate system to follow working plane changes. To deactivate working plane tracking, activate any other coordinate system (for example, **CSYS**,0 or **CSYS**,11).

**CSYS**,5 is a cylindrical coordinate system with global Cartesian Y as the axis of rotation. The local x, y and z axes are radial, θ, and axial (respectively). The R-Theta plane is the global X-Z plane, as it is for an axisymmetric model. Thus, at θ = 0.0, **CSYS**,5 has a specific orientation: the local x is in the global +X direction, local y is in the global -Z direction, and local z (the cylindrical axis) is in the global +Y direction.

**CSYS**,6 is a cylindrical coordinate system with global Cartesian X as the axis of rotation. The local x, y and z axes are axial, radial, and θ (respectively). The R-Theta plane is the global Y-Z plane, as it is for an axisymmetric model. Thus, at θ = 0.0, **CSYS**,6 has a specific orientation: the local x is in the global -Z direction, local y is in the global +Y direction, and local z (the cylindrical axis) is in the global +X direction.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CSYS.html
