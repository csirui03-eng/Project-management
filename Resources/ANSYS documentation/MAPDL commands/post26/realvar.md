---
apdl: "REALVAR"
method: realvar
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.realvar
generated: 2026-08-22
tags: [mapdl-command]
---

# REALVAR

PyMAPDL: `mapdl.realvar(ir='', ia='', name='', facta='', **kwargs)`

Forms a variable using only the real part of a complex variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**: Reference number of the variable to be operated on.

**name**: Thirty-two character name identifying the variable on printouts and displays. Embedded blanks are compressed for output.

**facta**: Scaling factor (positive or negative) applied to variable `IA` (defaults to 1.0).

## Notes

Forms a variable using only the real part of a variable. Used only with harmonic analyses ( [[antype|ANTYPE]],HARMIC).

Complex variables are stored in two-column arrays with the real component stored in the first column and the imaginary component stored in the second column. This command extracts the value stored in the first column (that is, real component). However with harmonic analyses, all variables are stored in two-column arrays as complex variables. If the variable is not complex, then the same value is stored in both columns. This command will extract the variable in the first column of the array, even if this variable is not the real component of a complex variable.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_REALVAR.html
