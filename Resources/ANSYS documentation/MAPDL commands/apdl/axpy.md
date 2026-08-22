---
apdl: "*AXPY"
method: axpy
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.axpy
generated: 2026-08-22
tags: [mapdl-command]
---

# *AXPY

PyMAPDL: `mapdl.axpy(vr='', vi='', m1='', wr='', wi='', m2='', **kwargs)`

Performs the matrix operation M2= v2M1 + w2M2.

## Parameters

**vr**, **vi**: The real and imaginary parts of the scalar `v`. Default value is 0.

**m1**: Name of matrix `M1`. If not specified, the operation M2 = w\*M2 will be performed.

**wr**, **wi**: The real and imaginary parts of the scalar `w`. Default value is 0.

**m2**: Name of matrix `M2`. Must be specified.

## Notes

### Argument descriptions

- `vr, vi : str` - The real and imaginary parts of the scalar `v`. Default value is 0.
- `m1 : str` - Name of matrix `M1`. If not specified, the operation M2 = w\*M2 will be performed.
- `wr, wi : str` - The real and imaginary parts of the scalar `w`. Default value is 0.
- `m2 : str` - Name of matrix `M2`. Must be specified.

The matrices `M1` and `M2` must have the same dimensions and same type (dense or sparse). If `M2` is real, `vi` and `wi` are ignored.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AXPY.html
