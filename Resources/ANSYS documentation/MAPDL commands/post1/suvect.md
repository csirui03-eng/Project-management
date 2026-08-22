---
apdl: "SUVECT"
method: suvect
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.suvect
generated: 2026-08-22
tags: [mapdl-command]
---

# SUVECT

PyMAPDL: `mapdl.suvect(rsetname='', lab1='', oper='', lab2='', offset='', **kwargs)`

Create new result data by operating on two existing result vectors on a given surface.

## Parameters

**rsetname**: Eight character name of the result data output. There will be one or three `RSetName` values depending on the operation specified in `Oper`.

**lab1**: Eight character name of the mapped data that forms vector 1. Specified sets must exist on all selected surfaces for this operation to take place. The names NORM and GC will be reserved for normals and for global (x, y, z).

**oper**

- `DOT` - Computes dot product between `lab1` and `lab2` vectors. The result is a scalar parameter ( `RSetName` ) and each value within the set can be modified (incremented) via `Offset`.
- `CROSS` - Computes cross product between `lab1` and `lab2` vectors. Each X, Y, Z value in the result can be modified (incremented) via `Offset`.
- `SMULT` - Scales (lab1x, lab1y, lab1z) vector by scalar `lab2`. Each X,Y,Z value in the result can be modified (incremented) via `Offset`.

**lab2**: Eight character name of the mapped data that forms vector 2. Sets with names Lab2X, Lab2Y, and Lab2Z must exist on all selected surfaces for operation to take place. For `Oper` = SMULT a scalar value or another predefined scalar item (for example, DA) can be supplied.

**offset**: An offset value to be applied to the resultant `RSetName`. One value is specified for `Oper` = DOT, and three values are specified for `Oper` = SMULT.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUVECT.html
