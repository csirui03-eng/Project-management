---
apdl: "CONJUG"
method: conjug
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.operations.Operations.conjug
generated: 2026-08-22
tags: [mapdl-command]
---

# CONJUG

PyMAPDL: `mapdl.conjug(ir='', ia='', name='', facta='', **kwargs)`

Forms the complex conjugate of a variable.

## Parameters

**ir**: Arbitrary reference number assigned to the resulting variable (2 to NV ( [[numvar|NUMVAR]] )). If this number is the same as for a previously defined variable, the previously defined variable will be overwritten with this result.

**ia**: Reference number of the variable to be operated on.

**name**: Thirty-two character name for identifying the variable on printouts and displays. Embedded blanks are compressed for output.

**facta**: Scaling factor (positive or negative) applied to variable (default to 1.0).

## Notes

Used only with harmonic analyses ( [[antype|ANTYPE]],HARMIC).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CONJUG.html
