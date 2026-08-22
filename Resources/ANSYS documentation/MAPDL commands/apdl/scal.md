---
apdl: "*SCAL"
method: scal
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.scal
generated: 2026-08-22
tags: [mapdl-command]
---

# *SCAL

PyMAPDL: `mapdl.scal(name='', val1='', val2='', **kwargs)`

Scales a vector or matrix by a constant.

## Parameters

**name**: Name used to identify the vector or matrix to be scaled. Must be specified.

**val1**: The real part of the constant to use (default = 1).

**val2**: The imaginary part of the constant to use (default = 0). This value is used only if the vector or matrix specified by `Name` is complex.

## Notes

This command can be applied to vectors and matrices created by the [[vec|*VEC]], [[dmat|*DMAT]] and [[smat|*SMAT]] commands.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SCAL.html
