---
apdl: "/XRANGE"
method: xrange
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.graphs.Graphs.xrange
generated: 2026-08-22
tags: [mapdl-command]
---

# /XRANGE

PyMAPDL: `mapdl.xrange(xmin='', xmax='', **kwargs)`

Specifies a linear abscissa (X) scale range.

## Parameters

**xmin**: Minimum abscissa scale value.

**xmax**: Maximum abscissa scale value.

## Notes

Specifies a linear abscissa (X) scale range for the line graph display. Use **/XRANGE**,DEFAULT to return to automatic scaling.

Automatic scaling will often yield inappropriate range values for logarithmic scales ( [[gropt|/GROPT]], LOGX).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_XRANGE.html
