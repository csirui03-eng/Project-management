---
apdl: "SQRT"
method: sqrt
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.sqrt
generated: 2026-08-22
tags: [mapdl-command]
---

# SQRT

PyMAPDL: `mapdl.sqrt(ir='', ia='', name='', facta='', **kwargs)`

Forms the square root of a variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**: Reference number of the variable to be operated on.

**name**: Thirty-two character name identifying the variable on printouts and displays. Embedded blanks are compressed for output.

**facta**: Scaling factor (positive or negative) applied to variable `IA` (defaults to 1.0).

## Notes

Forms the square root of a variable according to the operation:

(equation not available in the PyMAPDL source, see the Ansys help page)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SQRT.html
