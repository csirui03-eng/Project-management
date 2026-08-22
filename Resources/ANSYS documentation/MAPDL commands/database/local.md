---
apdl: "LOCAL"
method: local
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.coordinate_system.CoordinateSystem.local
generated: 2026-08-22
tags: [mapdl-command]
---

# LOCAL

PyMAPDL: `mapdl.local(kcn='', kcs='', xc='', yc='', zc='', thxy='', thyz='', thzx='', par1='', par2='', **kwargs)`

Defines a local coordinate system by a location and orientation.

## Parameters

**kcn**: Arbitrary reference number assigned to this coordinate system. Must be greater than 10. A coordinate system previously defined with this number will be redefined.

**kcs**

Coordinate system type:

- `0 or CART` - Cartesian
- `1 or CYLIN` - Cylindrical (circular or elliptical)
- `2 or SPHE` - Spherical (or spheroidal)
- `3 or TORO` - Toroidal

**xc**, **yc**, **zc**: Location (in the global Cartesian coordinate system) of the origin of the new coordinate system.

**thxy**: First rotation about local Z (positive X toward Y).

**thyz**: Second rotation about local X (positive Y toward Z).

**thzx**: Third rotation about local Y (positive Z toward X).

**par1**: Used for elliptical, spheroidal, or toroidal systems. If `KCS` = 1 or 2, `PAR1` is the ratio of the ellipse Y-axis radius to X-axis radius (defaults to 1.0 (circle)). If `KCS` = 3, `PAR1` is the major radius of the torus.

**par2**: Used for spheroidal systems. If `KCS` = 2, `PAR2` = ratio of ellipse Z-axis radius to X-axis radius (defaults to 1.0 (circle)).

## Notes

Defines a local coordinate system by origin location and orientation angles. The local coordinate system is parallel to the global Cartesian system unless rotated. Rotation angles are in degrees and redefine any previous rotation angles. See the [[clocal|CLOCAL]], [[cs|CS]], [[cswpla|CSWPLA]], and [[cskp|CSKP]] commands for alternate definitions. This local system becomes the active coordinate system ( [[csys|CSYS]] ). Local coordinate systems may be displayed with the [[psymb|/PSYMB]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LOCAL.html
