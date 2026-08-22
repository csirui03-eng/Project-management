---
apdl: "*INQUIRE"
method: starinquire
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.starinquire
generated: 2026-08-22
tags: [mapdl-command]
---

# *INQUIRE

PyMAPDL: `mapdl.starinquire(obj='', property_='', var1='', **kwargs)`

Retrieves properties of an existing APDL Math object.

## Parameters

**obj**: Name of the vector or matrix of interest.

**property_**

Object property to get:

- `DIM1` - First dimension of a matrix, or size of a vector.
- `DIM2` - Second dimension of a matrix.

**var1**: Name of the resulting parameter that contains the property value.

## Notes

The following example demonstrates using **\*INQUIRE** to get the number of rows and columns of an existing matrix.

``` apdl
*SMAT,K,D,IMPORT,FULL,file.full,STIFF  ! Import the stiffness matrix from an existing FULL file
*INQUIRE,K,DIM1,NROW                   ! Get the first dimension of the stiffness matrix
*INQUIRE,K,DIM2,NCOL                   ! Get the second dimension of the stiffness matrix
/COM, K matrix size: %NROW% x %NCOL%
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_INQUIRE_a.html
