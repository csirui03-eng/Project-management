---
apdl: "*MULT"
method: mult
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.mult
generated: 2026-08-22
tags: [mapdl-command]
---

# *MULT

PyMAPDL: `mapdl.mult(m1='', t1='', m2='', t2='', m3='', **kwargs)`

Performs the matrix multiplication M3 = M1 <sup>(T1)</sup> \*M2 <sup>(T2)</sup>.

## Parameters

**m1**: Name of matrix `M1`. Must have been previously specified by a [[dmat|*DMAT]] or [[smat|*SMAT]] command.

**t1**: Transpose key. Set `T1` = TRANS to use the non-conjugate transpose of `M1`. Set `T1` = CTRANS to use the conjugate transpose of `M1`. CTRANS is only applicable when the `M1` matrix is complex. If blank, transpose will not be used.

**m2**: Name of matrix `M2`. Must have been previously specified by a [[dmat|*DMAT]] command.

**t2**: Transpose key. Set `T2` = TRANS to use the non-conjugate transpose of `M2`. Set `T2` = CTRANS to use the conjugate transpose of `M2`. CTRANS is only applicable when the `M2` matrix is complex. If blank, transpose will not be used.

**m3**: Name of resulting matrix, `M3`. Must be specified.

## Notes

The matrices must be dimensionally consistent such that the number of columns of `M1` (or the transposed matrix, if requested) is equal to the number of rows of `M2` (or the transposed matrix, if requested).

You cannot multiply two sparse matrices with this command (that is, `M1` and `M2` cannot both be sparse). The resulting matrix, `M3`, will always be a dense matrix, no matter what combination of input matrices is used (dense\*sparse, sparse\*dense, or dense\*dense).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MULT.html
