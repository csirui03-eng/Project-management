---
apdl: "*REMOVE"
method: remove
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.remove
generated: 2026-08-22
tags: [mapdl-command]
---

# *REMOVE

PyMAPDL: `mapdl.remove(name='', val1='', val2='', val3='', **kwargs)`

Suppresses rows or columns of a dense matrix or a vector.

## Parameters

**name**: Name of the matrix or vector to be revised.

**val1**: First value index to suppress.

**val2**: Last value index to suppress.

**val3**

Specifies what to remove:

- `COL` - Remove columns of the matrix (default).
- `ROW` - Remove rows of the matrix.

## Notes

The values of the original matrix or vector specified by `Name` are retained. The matrix or vector is resized to the new number of rows and columns.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_REMOVE.html
