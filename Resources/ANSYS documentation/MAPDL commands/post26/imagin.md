---
apdl: "IMAGIN"
method: imagin
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.imagin
generated: 2026-08-22
tags: [mapdl-command]
---

# IMAGIN

PyMAPDL: `mapdl.imagin(ir='', ia='', name='', facta='', **kwargs)`

Forms an imaginary variable from a complex variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to `NV` ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**: Reference number of the variable to be operated on.

**name**: Thirty-two character name for identifying the variable on the printout and displays. Embedded blanks are compressed upon output.

**facta**: Scaling factor (positive or negative) applied to variable `IA` (defaults to 1.0).

## Notes

This command forms a new variable from a complex variable by storing the imaginary part as the real part. The imaginary part can then be used in other operations. Used only with harmonic analyses ( [[antype|ANTYPE]],HARMIC).

Complex variables are stored in two-column arrays with the real component stored in the first column and the imaginary component stored in the second column. This command extracts the value stored in the second column (that is, imaginary component). However, with harmonic analyses, all variables are stored in two-column arrays as complex variables. If the variable is not complex, then the same value is stored in both columns. This command will extract the variable in the second column of the array, even if this variable is not the imaginary component of a complex variable.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_IMAGIN.html
