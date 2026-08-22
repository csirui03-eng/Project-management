---
apdl: "*MERGE"
method: merge
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.merge
generated: 2026-08-22
tags: [mapdl-command]
---

# *MERGE

PyMAPDL: `mapdl.merge(name1='', name2='', val1='', val2='', **kwargs)`

Merges two dense matrices or vectors into one.

## Parameters

**name1**: Name of the matrix or vector to extend.

**name2**: Name of the matrix or vector to be merged into `Name1`.

**val1**: Row number indicating where the new values are to be inserted into the `Name1` vector.

**val2**

Specifies how the `Name2` matrix or vector is copied into the `Name1` matrix.

- `COL` - Insert the new values at the column location specified by `Val1` (default).
- `ROW` - Insert the new values at the row location specified by `Val1`.

## Notes

**\*MERGE** can be used to add new columns or rows to a dense matrix that was created by the [[dmat|*DMAT]] command. In this case, `Name1` must be the name of the dense matrix and `Name2` must refer to a vector or another dense matrix.

The following two examples demonstrate merging columns into a dense matrix.

(figure omitted, see the Ansys help page)

The following example demonstrates merging rows into a dense matrix.

(figure omitted, see the Ansys help page)

**\*MERGE** can also be used to add new rows to a vector that was created by the [[vec|*VEC]] command. In this case, `Name1` and `Name2` must both refer to vectors, as demonstrated in the example below.

(figure omitted, see the Ansys help page)

In all cases, the values of the original matrix or vector are retained, and the matrix or vector is resized to accommodate the additional rows or columns.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MERGE.html
