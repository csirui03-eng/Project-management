---
apdl: "VGET"
method: vget
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.special_purpose.SpecialPurpose.vget
generated: 2026-08-22
tags: [mapdl-command]
---

# VGET

PyMAPDL: `mapdl.vget(par='', ir='', tstrt='', kcplx='', **kwargs)`

Moves a variable into an array parameter vector.

## Parameters

**par**: Array parameter vector in the operation.

**ir**: Reference number of the variable (1 to NV ( [[numvar|NUMVAR]] )).

**tstrt**: Time (or frequency) corresponding to start of `IR` data. If between values, the nearer value is used.

**kcplx**

Complex number key:

- `0` - Use the real part of the `IR` data.
- `1` - Use the imaginary part of the `IR` data.

## Notes

Moves a variable into an array parameter vector. The starting array element number must be defined. For example, **VGET**,A(1),2 moves variable 2 (starting at time 0.0) to array parameter A. Looping continues from array element A(1) with the index number incremented by one until the variable is filled. The number of loops may be controlled with the [\*VLEN](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_VLEN.html#) [[vlen|*VLEN]] command (except that loop skipping ( `NINC` ) is not allowed). For multi-dimensioned array parameters, only the first (row) subscript is incremented.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VGET.html
