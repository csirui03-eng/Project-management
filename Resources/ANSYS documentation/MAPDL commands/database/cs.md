---
apdl: "CS"
method: cs
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.coordinate_system.CoordinateSystem.cs
generated: 2026-08-22
tags: [mapdl-command]
---

# CS

PyMAPDL: `mapdl.cs(kcn='', kcs='', norig='', nxax='', nxypl='', par1='', par2='', **kwargs)`

Defines a local coordinate system by three node locations.

## Parameters

**kcn**: Arbitrary reference number assigned to this coordinate system. Must be greater than 10. A coordinate system previously defined with this number will be redefined.

**kcs**

Coordinate system type:

- `0 or CART` - Cartesian
- `1 or CYLIN` - Cylindrical (circular or elliptical)
- `2 or SPHE` - Spherical (or spheroidal)
- `3 or TORO` - Toroidal

**norig**: Node defining the origin of this coordinate system. If `NORIG` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**nxax**: Node defining the positive x-axis orientation of this coordinate system.

**nxypl**: Node defining the x-y plane (with `NORIG` and `NXAX` ) in the first or second quadrant of this coordinate system.

**par1**: Used for elliptical, spheroidal, or toroidal systems. If `KCS` = 1 or 2, `PAR1` is the ratio of the ellipse Y-axis radius to X-axis radius (defaults to 1.0 (circle)). If `KCS` = 3, `PAR1` is the major radius of the torus.

**par2**: Used for spheroidal systems. If `KCS` = 2, `PAR2` = ratio of ellipse Z-axis radius to X-axis radius (defaults to 1.0 (circle)).

## Notes

Defines and activates a local right-handed coordinate system by specifying three existing nodes: to locate the origin, to locate the positive x-axis, and to define the positive x-y plane. This local system becomes the active coordinate system. See the [[clocal|CLOCAL]], [[cskp|CSKP]], [[cswpla|CSWPLA]], and [[local|LOCAL]] commands for alternate definitions. Local coordinate systems may be displayed with the [[psymb|/PSYMB]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CS.html
