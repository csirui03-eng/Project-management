---
apdl: "DSYS"
method: dsys
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.dsys
generated: 2026-08-22
tags: [mapdl-command]
---

# DSYS

PyMAPDL: `mapdl.dsys(kcn='', **kwargs)`

Activates a display coordinate system for geometry listings and plots.

**Command default:**

Global Cartesian ( `KCN` = 0) display coordinate system.

## Parameters

**kcn**: Coordinate system reference number. `KCN` may be 0,1,2 or any previously defined local coordinate system number. If a cylinder is displayed in its cylindrical coordinate system (with a 1,0,0 view), it will be unrolled (developed) into a flat plane (with theta along the Y direction).

## Notes

Boundary condition symbols, vector arrows, and element coordinate system triads are not transformed to the display coordinate system. The display system orientation (for the default view) is X horizontal to the right, Y vertical upward, and Z out of the screen (normal).

Line directions and area directions ( [[psymb|/PSYMB]],LDIR and [[psymb|/PSYMB]],ADIR) are not plotted for `KCN` \>0.

When you create 3D annotation, the coordinates are stored to the database in the display coordinate system that was active at the time of creation. Changing the display coordinate system does not change the annotation coordinate data in the database.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DSYS.html
