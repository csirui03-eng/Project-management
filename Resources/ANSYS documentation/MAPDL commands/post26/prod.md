---
apdl: "PROD"
method: prod
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.prod
generated: 2026-08-22
tags: [mapdl-command]
---

# PROD

PyMAPDL: `mapdl.prod(ir='', ia='', ib='', ic='', name='', facta='', factb='', factc='', **kwargs)`

Multiplies variables.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**, **ib**, **ic**: Reference numbers of the three variables to be operated on. If only two leave `IC` blank. If only one, leave `IB` blank also.

**name**: Thirty-two character name identifying the variable on printouts and displays. Embedded blanks are compressed for output.

**facta**, **factb**, **factc**: Scaling factors (positive or negative) applied to the corresponding variables (default to 1.0).

## Notes

Multiplies variables (up to three at once) according to the operation:

`IR` = ( `FACTA` x `IA` ) x ( `FACTB` x `IB` ) x ( `FACTC` x `IC` )

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PROD.html
