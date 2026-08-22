---
apdl: "VPUT"
method: vput
group: post26
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post26.special_purpose.SpecialPurpose.vput
generated: 2026-08-22
tags: [mapdl-command]
---

# VPUT

PyMAPDL: `mapdl.vput(par='', ir='', tstrt='', kcplx='', name='', **kwargs)`

Moves an array parameter vector into a variable.

## Parameters

**par**: Array parameter vector in the operation.

**ir**: Arbitrary reference number assigned to this variable (1 to `NV` ( [[numvar|NUMVAR]] )). Overwrites any existing results for this variable.

**tstrt**: Time (or frequency) corresponding to start of `IR` data. If between values, the nearer value is used.

**kcplx**

Complex number key:

- `0` - Use the real part of the `IR` data.
- `1` - Use the imaginary part of the `IR` data.

**name**: Thirty-two character name identifying the item on printouts and displays. Defaults to the label formed by concatenating VPUT with the reference number `IR`.

## Notes

At least one variable should be defined ( [[nsol|NSOL]], [[esol|ESOL]], [[rforce|RFORCE]], etc.) before using this command. The starting array element number must be defined. For example, **VPUT**,A(1),2 moves array parameter A to variable 2 starting at time 0.0. Looping continues from array element A(1) with the index number incremented by one until the variable is filled. Unfilled variable locations are assigned a zero value. The number of loops may be controlled with the [[vlen|*VLEN]] command (except that loop skipping (NINC) is not allowed). For multi-dimensioned array parameters, only the first (row) subscript is incremented.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VPUT.html
