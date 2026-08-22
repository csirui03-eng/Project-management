---
apdl: "WPLANE"
method: wplane
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.wplane
generated: 2026-08-22
tags: [mapdl-command]
---

# WPLANE

PyMAPDL: `mapdl.wplane(wn='', xorig='', yorig='', zorig='', xxax='', yxax='', zxax='', xplan='', yplan='', zplan='', **kwargs)`

Defines a working plane to assist in picking operations.

## Parameters

**wn**: Window number whose viewing direction will be modified to be normal to the working plane (defaults to 1). If `WN` is a negative value, the viewing direction will not be modified. If fewer than three points are used, the viewing direction of window `WN` will be used instead to define the normal to the working plane.

**xorig**, **yorig**, **zorig**: Global Cartesian coordinates of the origin of the working plane coordinate system.

**xxax**, **yxax**, **zxax**: Global Cartesian coordinates of a point defining the x-axis orientation. The x-axis aligns with the projection of the line from this orientation point to the origin.

**xplan**, **yplan**, **zplan**: Global Cartesian coordinates of the third point defining the working plane. This point will also define the location of the positive XY-sector of the working plane coordinate system.

## Notes

Defines a working plane to assist in picking operations using the coordinates of three noncolinear points. The three points also define the working plane coordinate system. A minimum of one point (the working plane origin) is required. Immediate mode may also be active. See [[wpstyl|WPSTYL]] command to set the style of working plane display.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_WPLANE.html
