---
apdl: "/GRTYP"
method: grtyp
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.graphs.Graphs.grtyp
generated: 2026-08-22
tags: [mapdl-command]
---

# /GRTYP

PyMAPDL: `mapdl.grtyp(kaxis='', **kwargs)`

Selects single or multiple Y-axes graph displays.

## Parameters

**kaxis**

Axis selection key:

- `0 or 1` - Single Y-axis. Up to 10 curves scaled to a single Y-axis.
- `2` - Additional Y-axes (one for each curve) (3 curves maximum). Allows better scaling of curves with widely differing numbering ranges.
- `3` - Same as 2 but with additional Y-axis and curves projected out of the plane (6 curves maximum). Allows clearer display with an isometric view. The default view when `KAXIS` = 3 is View,1,1,2,3.

## Notes

The basic line graph has one or more curves plotted against the same Y and X axes. Multiple curve graphs can also be plotted with individual Y axes and the same X axis. The Y axis of the first curve is referred to as the base Y-axis and the Y axes of the other curves as additional Y axes. Curves are numbered sequentially from 1 (the base curve) in the order in which they are displayed. See the [[axlab|/AXLAB]], [[gropt|/GROPT]], [[grid|/GRID]], and [[gthk|/GTHK]] commands for other display options.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GRTYP.html
