---
apdl: "LARGE"
method: large
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.large
generated: 2026-08-22
tags: [mapdl-command]
---

# LARGE

PyMAPDL: `mapdl.large(ir='', ia='', ib='', ic='', name='', facta='', factb='', factc='', **kwargs)`

Finds the largest (the envelope) of three variables.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**, **ib**, **ic**: Reference numbers of the three variables to be operated on. If only two, leave `IC` blank. If only one, leave `IB` blank also.

**name**: Thirty-two character name for identifying the variable on the printout and displays. Embedded blanks are compressed upon output.

**facta**, **factb**, **factc**: Scaling factors (positive or negative) applied to the corresponding variables (default to 1.0).

## Notes

Creates a new variable by finding the largest of up to three variables according to the operation:

`IR` = Largest of ( `FACTA` x `IA`, `FACTB` x `IB`, `FACTC` x `IC` )

The comparison is done at each time location, so that the new variable is the "envelope" of the three existing variables.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LARGE.html
