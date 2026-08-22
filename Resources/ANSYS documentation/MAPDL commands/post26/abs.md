---
apdl: "ABS"
method: abs
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.abs
generated: 2026-08-22
tags: [mapdl-command]
---

# ABS

PyMAPDL: `mapdl.abs(ir='', ia='', name='', facta='', **kwargs)`

Forms the absolute value of a variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**: Reference number of the variable to be operated on.

**name**: Thirty-two character name for identifying the variable on the printout and displays. Embedded blanks are compressed upon output.

**facta**: Scaling factor (positive or negative) applied to variable `IA` (defaults to 1.0).

## Notes

The new variable is calculated as:

IR = \| FACTA x IA \|

For a complex number (a + i b), the absolute value is the magnitude, where the `IA` values are obtained from:

(equation not available in the PyMAPDL source, see the Ansys help page)

See [POST26 - Data Operations](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_post10.html#eqbe42048a-448b-4de9-91a9-1c8007937622) in the [Mechanical APDL Theory Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_thry/thy_biblio.html) for details.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ABS.html
