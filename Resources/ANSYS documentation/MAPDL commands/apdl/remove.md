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

### Argument descriptions

- `name : str` - Name of the matrix or vector to be revised.
- `val1, val2, val3 : str` - Additional input. The meaning of `Val1` to `Val3` varies depending on the entity type (matrix or vector). See details below.

**The following** `Val1` through `Val3` fields are used if `Name` refers to a dense matrix created by the [[dmat|*DMAT]] command:

- `val1 : str` - First row or column number to suppress.
- `val2 : str` - Last row or column number to suppress.
- `val3 : str` - Specifies what to remove:
  - `COL` - Remove columns of the matrix (default).
  - `ROW` - Remove rows of the matrix.

**The following** `Val1` and `Val2` fields are used if `Name` refers to a vector created by the [[vec|*VEC]] command:

- `val1 : str` - First value index to suppress.
- `val2 : str` - Last value index to suppress.

The values of the original matrix or vector specified by `Name` are retained. The matrix or vector is resized to the new number of rows and columns.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_REMOVE.html
