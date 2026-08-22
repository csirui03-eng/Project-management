---
apdl: "ADD"
method: add
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.add
generated: 2026-08-22
tags: [mapdl-command]
---

# ADD

PyMAPDL: `mapdl.add(ir='', ia='', ib='', ic='', name='', facta='', factb='', factc='', **kwargs)`

Adds (sums) variables.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**, **ib**, **ic**: Reference numbers of the three variables to be operated on. If only two variables, leave `IC` blank. If only one, leave `IB` and `IC` blank.

**name**: Thirty-two character name for identifying the variable on the printout and displays. Embedded blanks are compressed upon output.

**facta**, **factb**, **factc**: Scaling factors (positive or negative) applied to the corresponding variables (default to 1.0).

## Notes

Adds variables (up to three at once) according to the operation:

`IR` = ( `FACTA` x `IA` ) + ( `FACTB` x `IB` ) + ( `FACTC` x `IC` )

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ADD.html
