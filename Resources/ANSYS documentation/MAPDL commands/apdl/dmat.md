---
apdl: "*DMAT"
method: dmat
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.dmat
generated: 2026-08-22
tags: [mapdl-command]
---

# *DMAT

PyMAPDL: `mapdl.dmat(matrix='', type_='', method='', val1='', val2='', val3='', val4='', val5='', **kwargs)`

Creates a dense matrix.

## Parameters

**matrix**: Name used to identify the matrix. Must be specified.

**type_**

Matrix type:

- `D` - Double precision real values (default).
- `Z` - Complex double precision values.
- `I` - Integer values.

**method**

Method used to create the matrix:

- `ALLOC` - Allocate space for a matrix (default).
- `RESIZE` - Resize an existing matrix to new row and column dimensions. Values are kept from the original matrix. If the dimensions specified by `Val1` (rows) and `Val2` (columns) are greater than the original matrix size, the additional entries are assigned a value of zero.
- `COPY` - Copy an existing matrix.
- `LINK` - Link to an existing matrix. The memory will be shared between the original matrix and the new matrix. This is useful for manipulating a submatrix of a larger matrix. The `Val1` through `Val5` arguments will be used to specify the lower and upper bounds of row and column numbers from the original matrix.
- `IMPORT` - Import the matrix from a file.

**val1**: Name of the original matrix.

**val2**: First column number (defaults to 1).

**val3**: Last column number (defaults to the maximum column number of the original matrix).

**val4**: First row number (defaults to 1).

**val5**: Last row number (defaults to the maximum row number of the original matrix).

## Notes

This command allows you to create a dense matrix. To create a sparse matrix, use the [[smat|*SMAT]] command. [[smat|*SMAT]] is recommended for large matrices obtained from the `.FULL` or `.HBMAT` file. Refer to the [[hbmat|HBMAT]] command documentation for more information about `.FULL` file contents.

Use the [[vec|*VEC]] command to create a vector.

For very large matrices, use the OUTOFCORE option ( `Method` = ALLOC or COPY) to keep some of the matrix on disk if there is insufficient memory.

When importing a dense matrix from a **DMIG** file, you can define the formatting of the file using the `Val3` and `Val4` fields. Here are a few different example of formats:

- A LARGE field format file (using `Val3` = `LARGE`):

``` apdl
...    DMIG*   KAAX                          21               2    *                     21
1-2.261491337E+08...
```

- A FREE field format file with blank separators (using `Val4` = `S`):

``` apdl
...    DMIG stiff 1 2 1 2 29988.    1 6 149940. 2 2 -29988.    2 6 149940.    ...
```

- A FREE field format file with a comma separator (using `Val4` = `,`):

``` apdl
...    DMIG,KF,22321,3,,22321,2,-5.00E+6    DMIG,KF,22320,3,,22320,2,-5.00E+6    ...
```

**Requirement when importing matrices from a Nastran DMIG file:** To ensure that the `.sub` file is properly generated from matrices imported from Nastran **DMIG** file, the generalized coordinates for a CMS superelement (SPOINTS in Nastran) must appear last (have highest ID number).

**Example Usage** [APDL Math Examples](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdlmathex.html#apdlmath_partfact)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DMAT.html
