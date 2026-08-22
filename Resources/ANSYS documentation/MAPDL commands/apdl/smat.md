---
apdl: "*SMAT"
method: smat
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.smat
generated: 2026-08-22
tags: [mapdl-command]
---

# *SMAT

PyMAPDL: `mapdl.smat(matrix='', type_='', method='', val1='', val2='', val3='', val4='', val5='', **kwargs)`

Creates a sparse matrix.

## Parameters

**matrix**: Name used to identify the matrix. Must be specified.

**type_**

Matrix type:

- `D` - Double precision real values (default).
- `Z` - Complex double precision values.

**method**

Method used to create the matrix:

- `ALLOC` - Allocate a new matrix.
- `COPY` - Copy an existing matrix.
- `IMPORT` - Import the matrix from a file.

**val1**: Name of the matrix to copy (can be either a dense or a sparse matrix).

**val2**

Method used for copying the matrix:

- `DIAG` - Copy only the diagonal of the matrix. `Val3` and `Val4` are ignored.
- `TRANS` - Transpose the original matrix. `Val3` and `Val4` are ignored.
- `EXTRACT` - Extract a submatrix based on row and column numbers specified by `Val3` and `Val4`.

**val3**: Name of integer vector ( [[vec|*VEC]] ) containing row numbers. If no vector is specified, defaults to all rows.

**val4**: Name of integer vector ( [[vec|*VEC]] ) containing column numbers. If no vector is specified, defaults to all columns.

**val5**: Additional input. The meaning of `Val1` through `Val5` will vary depending on the specified `Method`. See details below.

## Notes

Use the [[dmat|*DMAT]] command to create a dense matrix.

For more information on the CSR format, see [Creating a Sparse Matrix Using the CSR Format](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdlCSRformat.html#eqdaaeaade-718e-4f25-b7ce-ba5a1903b1bf)

For more information on the NOD2SOLV and USR2SOLV mapping vectors, see.

For more information about `.FULL` file contents, see the [[hbmat|HBMAT]] in the [Command Reference](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_Z_TOC.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SMAT.html
