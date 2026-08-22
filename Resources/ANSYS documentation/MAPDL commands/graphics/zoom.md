---
apdl: "/ZOOM"
method: zoom
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.views.Views.zoom
generated: 2026-08-22
tags: [mapdl-command]
---

# /ZOOM

PyMAPDL: `mapdl.zoom(wn='', lab='', x1='', y1='', x2='', y2='', **kwargs)`

Zooms a region of a display window.

## Parameters

**wn**: Window number to which command applies (defaults to 1).

**lab**

Label to define the desired type of zoom:

- `OFF` - Turns zoom off (refits image of entire model to the window).
- `BACK` - Goes back to previous zoom setting (five successive back ups, maximum).
- `SCRN` - Interprets X1,Y1 as the screen coordinates of the center of a square zoom region; X2,Y2 as the screen coordinates of a point on one side of that square.
- `RECT` - Interprets X1,Y1 and X2,Y2 as the screen coordinates of two opposite corners of a rectangular zoom region.

**x1**, **y1**, **x2**, **y2**: The description of the argument is missing in the Python function. Please, refer to the [command documentation](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ZOOM.html) for further information.

## Notes

Zooms (centers and magnifies) the specified region of a display window. **/ZOOM** will operate on a display that has been formed by an explicit graphics action command ( [[aplot|APLOT]], [[eplot|EPLOT]], etc.). **/ZOOM** has no effect on an "immediate" graphics display. When **/ZOOM** is executed, the display is automatically replotted such that the specified zoom region is centered and sized to fill the window.

Auto resizing is disabled when you issue the **/ZOOM** command. To restore auto resizing, issue the [[auto|/AUTO]] command, or select FIT from the [Pan, Zoom, Rotate](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_wid/Hlp_UI_PanZoom.html#wpanzoomk) box.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ZOOM.html
