---
apdl: "/VIEW"
method: view
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.view
generated: 2026-08-22
tags: [mapdl-command]
---

# /VIEW

PyMAPDL: `mapdl.view(wn='', xv='', yv='', zv='', **kwargs)`

Defines the viewing direction for the display.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**xv**, **yv**, **zv**: The object is viewed along the line from point `XV`, `YV`, `ZV` (in the global coordinate system) to the global coordinate system origin. For section displays, the cutting plane is assumed to be perpendicular to this line. If `XV` = WP, modify view to be normal to the currently defined working plane. Defaults to (0,0,1).

## Notes

The view line is always normal to the screen. The view is selected by defining a point (in the global Cartesian coordinate system) representing a point along the viewing line. This point, and the global Cartesian coordinate system origin, define the line along which the object is viewed while looking toward the origin. Any point along the view line may be used, that is, (1,1,1) and (2,2,2) give the same view. The display orientation may be changed as desired ( [[angle|/ANGLE]] ). The display coordinate system type may be changed (from Cartesian to cylindrical, spherical, toroidal, etc.) with the [[dsys|DSYS]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VIEW.html
