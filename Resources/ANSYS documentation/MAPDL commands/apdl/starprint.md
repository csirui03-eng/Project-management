---
apdl: "*PRINT"
method: starprint
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.starprint
generated: 2026-08-22
tags: [mapdl-command]
---

# *PRINT

PyMAPDL: `mapdl.starprint(matrix='', fname='', **kwargs)`

Prints the matrix values to a file.

## Parameters

**matrix**: Name of matrix or vector to print. Must be specified.

**fname**: File name (case-sensitive, 32-character maximum). If blank, matrix is written to the output file.

## Notes

### Argument descriptions

- `matrix : str` - Name of matrix or vector to print. Must be specified.
- `fname : str` - File name (case-sensitive, 32-character maximum). If blank, matrix is written to the output file.

The matrix may be a dense matrix ( [[dmat|*DMAT]] ), a sparse matrix ( [[smat|*SMAT]] ), or a vector ( [[vec|*VEC]] ). Only the non-zero entries of the matrix are printed.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRINT_a.html
