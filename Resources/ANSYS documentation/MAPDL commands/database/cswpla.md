---
apdl: "CSWPLA"
method: cswpla
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.coordinate_system.CoordinateSystem.cswpla
generated: 2026-08-22
tags: [mapdl-command]
---

# CSWPLA

PyMAPDL: `mapdl.cswpla(kcn='', kcs='', par1='', par2='', **kwargs)`

Defines a local coordinate system at the origin of the working plane.

## Parameters

**kcn**: Arbitrary reference number assigned to this coordinate system. Must be greater than 10. A coordinate system previously defined with this number will be redefined.

**kcs**

Coordinate system type:

- `0 or CART` - Cartesian
- `1 or CYLIN` - Cylindrical (circular or elliptical)
- `2 or SPHE` - Spherical (or spheroidal)
- `3 or TORO` - Toroidal

**par1**: Used for elliptical, spheroidal, or toroidal systems. If `KCS` = 1 or 2, `PAR1` is the ratio of the ellipse Y-axis radius to X-axis radius (defaults to 1.0 (circle)). If `KCS` = 3, `PAR1` is the major radius of the torus.

**par2**: Used for spheroidal systems. If `KCS` = 2, `PAR2` = ratio of ellipse Z-axis radius to X-axis radius (defaults to 1.0 (circle)).

## Notes

Defines and activates a local right-handed coordinate system centered at the origin of the working plane. The coordinate system's local x-y plane (for a Cartesian system) or R-θ plane (for a cylindrical or spherical system) corresponds to the working plane. This local system becomes the active coordinate system. See the [[cs|CS]], [[local|LOCAL]], [[clocal|CLOCAL]], and [[cskp|CSKP]] commands for alternate ways to define a local coordinate system. Local coordinate systems may be displayed with the [[psymb|/PSYMB]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CSWPLA.html
