---
apdl: "/GCOLUMN"
method: gcolumn
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.set_up.SetUp.gcolumn
generated: 2026-08-22
tags: [mapdl-command]
---

# /GCOLUMN

PyMAPDL: `mapdl.gcolumn(curve='', string='', **kwargs)`

Allows the user to apply a label to a specified curve.

## Parameters

**curve**: Curve number on which label will be applied (integer value between 1 and 10).

**string**: Name or designation that will be applied to the curve (8 characters max).

## Notes

This command is used for an array parameter plot (a plot created by the [[starvplot|*VPLOT]] command). Normally the label for curve 1 is COL 1, the label for curve 2 is COL 2 and so on; the column number is the field containing the dependent variables for that particular curve. Issuing **/GCOLUMN**, `CURVE`, with no string value specified resets the label to the original value.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GCOLUMN.html
