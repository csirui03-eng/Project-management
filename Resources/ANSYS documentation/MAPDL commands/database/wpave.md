---
apdl: "WPAVE"
method: wpave
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.wpave
generated: 2026-08-22
tags: [mapdl-command]
---

# WPAVE

PyMAPDL: `mapdl.wpave(x1='', y1='', z1='', x2='', y2='', z2='', x3='', y3='', z3='', **kwargs)`

Moves the working plane origin to the average of specified points.

## Parameters

**x1**, **y1**, **z1**: Coordinates (in the active coordinate system) of the first point. If `X1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**x2**, **y2**, **z2**: Coordinates (in the active coordinate system) of the second point.

**x3**, **y3**, **z3**: Coordinates (in the active coordinate system) of the third point.

## Notes

Moves the origin of the working plane to the average of the specified points. A point is considered specified only if at least one of its coordinates is non-blank, and at least one point (1, 2, or 3) must be specified. Blank coordinates of a specified point are assumed to be zero. Averaging is based on the active coordinate system.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WPAVE.html
