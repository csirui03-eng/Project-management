---
apdl: "/YRANGE"
method: yrange
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.graphs.Graphs.yrange
generated: 2026-08-22
tags: [mapdl-command]
---

# /YRANGE

PyMAPDL: `mapdl.yrange(ymin='', ymax='', num='', **kwargs)`

Specifies a linear ordinate (Y) scale range.

## Parameters

**ymin**: Minimum ordinate scale value.

**ymax**: Maximum ordinate scale value.

**num**: Y-axis number to which range applies (defaults to 1). Valid numbers are 1 to 3 for [[grtyp|/GRTYP]],2 and 1 to 6 for [[grtyp|/GRTYP]],3. If ALL, apply to all Y-axes.

## Notes

Specifies a linear ordinate (Y) scale range for the line graph display. Use **/YRANGE**,DEFAULT to return to automatic scaling. For multiple Y-axes graphs ( [[grtyp|/GRTYP]] ), see [[gropt|/GROPT]], ASCAL to automatically scale the additional Y-axes.

Automatic scaling will often yield inappropriate range values for logarithmic scales ( [[gropt|/GROPT]], LOGY).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_YRANGE.html
