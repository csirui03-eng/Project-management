---
apdl: "*INIT"
method: init
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.init
generated: 2026-08-22
tags: [mapdl-command]
---

# *INIT

PyMAPDL: `mapdl.init(name='', method='', val1='', val2='', val3='', **kwargs)`

Initializes a vector or matrix.

## Parameters

**name**: Vector or matrix which will be initialized. This can be a vector (created by the [[vec|*VEC]] command), a dense matrix (created by the [[dmat|*DMAT]] command), or a sparse matrix (created by the [[smat|*SMAT]] command).

**method**

Initialization method to use:

- `ZERO` - Fill the vector/matrix with zeros (default).
- `CONST` - Fill the vector/matrix with a constant value.
- `RAND` - Fill the vector/matrix with random values.
- `DIAG` - Fill the `n` th diagonal of the matrix with a constant value. Other values are not overwritten. For this option, `Name` must be a dense matrix.
- `ADIAG` - Fill the `n` th anti-diagonal of the matrix with a constant value. Other values are not overwritten. For this option, `Name` must be a dense matrix.
- `CONJ` - Take the complex conjugate of the values in the vector/matrix (no change for non- complex values).
- `FILTER` - Initialize a subset of values of a vector using a filtering vector. For this option, `Name` must be a vector.

**val1**: The name of an existing integer vector (created by [[vec|*VEC]] ) to be used as the filter vector. The values in this vector indicate the locations in the `Name` vector that are to be initialized to `Val2` (real value) and `Val3` (imaginary value, if applicable). Location values higher than the dimension of the original vector are ignored.

**val2**: The real part of the value used for initialization (default = 0).

**val3**: The imaginary part of the value used for initialization (default = 0); applicable only if the `Name` vector contains complex values.

## Notes

### Argument descriptions

- `name : str` - Vector or matrix which will be initialized. This can be a vector (created by the [[vec|*VEC]] command), a dense matrix (created by the [[dmat|*DMAT]] command), or a sparse matrix (created by the [[smat|*SMAT]] command).
- `method : str` - Initialization method to use:
  - `ZERO` - Fill the vector/matrix with zeros (default).
  - `CONST` - Fill the vector/matrix with a constant value.
  - `RAND` - Fill the vector/matrix with random values.
  - `DIAG` - Fill the `n` th diagonal of the matrix with a constant value. Other values are not overwritten. For this option, `Name` must be a dense matrix.
  - `ADIAG` - Fill the `n` th anti-diagonal of the matrix with a constant value. Other values are not overwritten. For this option, `Name` must be a dense matrix.
  - `CONJ` - Take the complex conjugate of the values in the vector/matrix (no change for non- complex values).
  - `FILTER` - Initialize a subset of values of a vector using a filtering vector. For this option, `Name` must be a vector.
- `val1, val2, val3 : str` - Additional input. The meaning of `Val1` through `Val3` will vary depending on the specified `Method`. See details below.

**The following** `Valx` fields are used with `Method` = CONST:

- `val1 : str` - The real part of the constant value to use (default = 0).
- `val2 : str` - The imaginary part of the constant value to use (default = 0). Required only for a complex vector/matrix.

**The following** `Valx` fields are used with `Method` = DIAG or `Method` = ADIAG:

- `val1 : str` - The number of the diagonal to fill. A zero value (which is the default) indicates the main diagonal (or main anti-diagonal). A positive value indicates an upper diagonal; a negative value indicates a lower diagonal.
- `val2 : str` - The real part of the constant value to use (default = 1).
- `val3 : str` - The imaginary part of the constant value to use (default = 0). Required only for a complex matrix.

The following example demonstrates `Method` = DIAG:

(figure omitted, see the Ansys help page)

**The following** `Valx` fields are used with `Method` = FILTER:

- `val1 : str` - The name of an existing integer vector (created by [[vec|*VEC]] ) to be used as the filter vector. The values in this vector indicate the locations in the `Name` vector that are to be initialized to `Val2` (real value) and `Val3` (imaginary value, if applicable). Location values higher than the dimension of the original vector are ignored.
- `val2 : str` - The real part of the value used for initialization (default = 0).
- `val3 : str` - The imaginary part of the value used for initialization (default = 0); applicable only if the `Name` vector contains complex values.

This command initializes a previously defined vector ( [[vec|*VEC]] ), dense matrix ( [[dmat|*DMAT]] ), or sparse matrix ( [[smat|*SMAT]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INIT.html
