---
apdl: "/ANGLE"
method: angle
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.angle
generated: 2026-08-22
tags: [mapdl-command]
---

# /ANGLE

PyMAPDL: `mapdl.angle(wn='', theta='', axis='', kincr='', **kwargs)`

Rotates the display about an axis.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**theta**: Angle (degrees) for changing display orientation (positive, counterclockwise about specified axis).

**axis**: Rotation axis: XS, YS, or ZS (default) for the screen axes; XM, YM, or ZM for the global Cartesian model axes. ZS is normal to the screen; all axes pass through the focus point.

**kincr**

Cumulative rotation key:

- `0` - Do not use cumulative successive rotations.
- `1` - Use cumulative rotations. Rotations are relative to the previous rotation. View settings ( [[view|/VIEW]] ) are recalculated.

## Notes

Default orientation is YS vertical. When the [[xfrm|/XFRM]] command is set for rotation about two points, or for entities, the **/ANGLE** command is functional only for `Axis` = ZS or ZM and `KINCR` = 1.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ANGLE.html
