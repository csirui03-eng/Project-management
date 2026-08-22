---
apdl: "QUOT"
method: quot
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.quot
generated: 2026-08-22
tags: [mapdl-command]
---

# QUOT

PyMAPDL: `mapdl.quot(ir='', ia='', ib='', name='', facta='', factb='', **kwargs)`

Divides two variables.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**, **ib**: Reference numbers of the two variables to be operated on.

**name**: Thirty-two character name identifying the variable on printouts and displays. Embedded blanks are compressed for output.

**facta**, **factb**: Scaling factors (positive or negative) applied to the corresponding variables (default to 1.0).

## Notes

Divides two variables according to the operation:

`IR` = ( `FACTA` x `IA` )/( `FACTB` x `IB` )

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_QUOT.html
