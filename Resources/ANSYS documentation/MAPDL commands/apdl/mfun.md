---
apdl: "*MFUN"
method: mfun
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.mfun
generated: 2026-08-22
tags: [mapdl-command]
---

# *MFUN

PyMAPDL: `mapdl.mfun(parr='', func='', par1='', **kwargs)`

Copies or transposes an array parameter matrix.

## Parameters

**parr**: The name of the resulting array parameter matrix. See [[starset|*SET]] for name restrictions.

**func**

Copy or transpose function:

- `COPY` - `Par1` is copied to `ParR`
- `TRAN` - `Par1` is transposed to `ParR`. Rows (m) and columns (n) of `Par1` matrix are transposed to resulting `ParR` matrix of shape (n,m).

**par1**: Array parameter matrix input to the operation.

## Notes

Operates on one input array parameter matrix and produces one output array parameter matrix according to: `ParR` = f( `Par1` )

where the function (f) is either a copy or transpose, as described above.

Functions are based on the standard FORTRAN definitions where possible. `ParR` may be the same as `Par1`. Starting array element numbers must be defined for each array parameter matrix if it does not start at the first location. For example, **\*MFUN**,A(1,5),COPY,B(2,3) copies matrix B (starting at element (2,3)) to matrix A (starting at element (1,5)). The diagonal corner elements for each submatrix must be defined: the upper left corner by the array starting element (on this command), the lower right corner by the current values from the [[vcol|*VCOL]] and [[vlen|*VLEN]] commands. The default values are the (1,1) element and the last element in the matrix. No operations progress across matrix planes (in the 3rd dimension). Absolute values and scale factors may be applied to all parameters ( [[vabs|*VABS]], [[vfact|*VFACT]] ). Results may be cumulative ( [[vcum|*VCUM]] ). Array elements should not be skipped with the [[vmask|*VMASK]] and the `NINC` value of the [[vlen|*VLEN]] specifications. The number of rows ( [[vlen|*VLEN]] ) applies to the `Par1` array. See the [[voper|*VOPER]] command for details.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MFUN.html
