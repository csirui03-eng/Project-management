---
apdl: "PRANGE"
method: prange
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.prange
generated: 2026-08-22
tags: [mapdl-command]
---

# PRANGE

PyMAPDL: `mapdl.prange(linc='', vmin='', vmax='', xvar='', **kwargs)`

Determines the path range.

**Command default:**

Include every interpolation point and entire path distance.

## Parameters

**linc**, **vmin**, **vmax**: Set the range for listing or displaying the table locations between a minimum value ( `VMIN` ) and a maximum value ( `VMAX` ) of the path distance with a location increment of `LINC` (defaults to 1). The first location begins at `VMIN`.

**xvar**: Path variable item to be used as the x-axis plot variable. Any valid path variable may be used ( [[pdef|PDEF]] command). Default variable is the path distance, S.

## Notes

Determines the path distance range for use with the [[prpath|PRPATH]] and [[plpath|PLPATH]] commands.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRANGE.html
