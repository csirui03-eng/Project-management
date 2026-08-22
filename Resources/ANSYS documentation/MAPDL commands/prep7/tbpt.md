---
apdl: "TBPT"
method: tbpt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbpt
generated: 2026-08-22
tags: [mapdl-command]
---

# TBPT

PyMAPDL: `mapdl.tbpt(oper='', x1='', x2='', x3='', xn='', **kwargs)`

Defines a point on a nonlinear data curve.

## Parameters

**oper**

Operation to perform:

- `DEFI` - Defines a new data point (default). The point is inserted into the table in ascending order of `X1`. If a point already exists with the same `X1` value, it is replaced.
- `DELE` - Deletes an existing point. The `X1` value must match the `X1` value of the point to be deleted ( `XN` is ignored).

**x1**, **x2**, **x3**, **xn**: The N components of the point. N depends on the type of data table. Except for [[tb|TB]],EXPE all other [[tb|TB]] Tables support only 2 components.

## Notes

**TBPT** defines a point on a nonlinear data curve (such as a stress-strain curve, B-H curve, etc.) at the temperature specified on the last [[tbtemp|TBTEMP]] command. The meaning of the values depends on the type of data table specified on the last [[tb|TB]] command.

This command is also valid in SOLUTION.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBPT.html
