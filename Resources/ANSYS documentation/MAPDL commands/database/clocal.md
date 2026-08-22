---
apdl: "CLOCAL"
method: clocal
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.coordinate_system.CoordinateSystem.clocal
generated: 2026-08-22
tags: [mapdl-command]
---

# CLOCAL

PyMAPDL: `mapdl.clocal(kcn='', kcs='', xl='', yl='', zl='', thxy='', thyz='', thzx='', par1='', par2='', **kwargs)`

Defines a local coordinate system relative to the active coordinate system.

## Parameters

**kcn**: Arbitrary reference number assigned to this coordinate system. Must be greater than 10. A coordinate system previously defined with this number will be redefined.

**kcs**

Coordinate system type:

- `0 or CART` - Cartesian
- `1 or CYLIN` - Cylindrical (circular or elliptical)
- `2 or SPHE` - Spherical (or spheroidal)
- `3 or TORO` - Toroidal

**xl**, **yl**, **zl**: Location (in the active coordinate system) of the origin of the new coordinate system (R, θ, Z for cylindrical, R, θ,Φ for spherical or toroidal).

**thxy**: First rotation about local Z (positive X toward Y).

**thyz**: Second rotation about local X (positive Y toward Z).

**thzx**: Third rotation about local Y (positive Z toward X).

**par1**: Used for elliptical, spheroidal, or toroidal systems. If `KCS` = 1 or 2, `PAR1` is the ratio of the ellipse Y-axis radius to X-axis radius (defaults to 1.0 (circle)). If `KCS` = 3, `PAR1` is the major radius of the torus.

**par2**: Used for spheroidal systems. If `KCS` = 2, `PAR2` = ratio of ellipse Z-axis radius to X-axis radius (defaults to 1.0 (circle)).

## Notes

Defines and activates a local coordinate system by origin location and orientation angles relative to the active coordinate system. This local system becomes the active coordinate system, and is automatically aligned with the active system (that is, x is radial if a cylindrical system is active, etc.). Nonzero rotation angles (degrees) are relative to this automatic rotation. See the [[cs|CS]], [[cskp|CSKP]], [[cswpla|CSWPLA]], and [[local|LOCAL]] commands for alternate definitions. Local coordinate systems may be displayed with the [[psymb|/PSYMB]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CLOCAL.html
