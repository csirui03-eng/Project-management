---
apdl: "*VEC"
method: vec
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.vec
generated: 2026-08-22
tags: [mapdl-command]
---

# *VEC

PyMAPDL: `mapdl.vec(vector='', type_='', method='', val1='', val2='', val3='', val4='', **kwargs)`

Creates a vector.

## Parameters

**vector**: Name used to identify the vector. Must be specified.

**type_**

Vector type:

- `D` - Double precision real values (default).
- `Z` - Complex double precision values.
- `I` - Integer values.

**method**

Method used to create the vector:

- `ALLOC` - Allocate space for a vector (default).
- `RESIZE` - Resize an existing vector to a new length. Values are kept from the original vector. If the length specified by `Val1` is greater than the original vector length, the additional rows are assigned a value of zero.
- `COPY` - Copy an existing vector.
- `IMPORT` - Import the vector from a file.
- `LINK` - Link to a column of an existing dense [[dmat|*DMAT]] matrix and use it in subsequent vector calculations. Any changes to the vector are also made to the corresponding matrix column (memory is shared).

**val1**: Name of the [[dmat|*DMAT]] matrix.

**val2**: Column number of the matrix to link to.

**val3**, **val4**: Additional input. The meaning of `Val1` through `Val5` will vary depending on the specified `Method`. See details below.

## Notes

Use the [[dmat|*DMAT]] command to create a matrix.

For more information on the BACK and FORWARD nodal mapping vectors, see in the [Ansys Parametric Design Language Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_apdl/apdlxpl.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VEC.html
