---
apdl: "*NRM"
method: nrm
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.nrm
generated: 2026-08-22
tags: [mapdl-command]
---

# *NRM

PyMAPDL: `mapdl.nrm(name='', normtype='', parr='', normalize='', **kwargs)`

Computes the norm of the specified matrix or vector.

## Parameters

**name**: Matrix or vector for which the norm will be computed. This can be a dense matrix (created by the [[dmat|*DMAT]] command), a sparse matrix (created by the [[smat|*SMAT]] command) or a vector (created by the [[vec|*VEC]] command)

**normtype**

Mathematical norm to use:

- `NRM2` - L2 (Euclidian or SRSS) norm (default).
- `NRM1` - L1 (absolute sum) norm (vectors and dense matrices only).
- `NRMINF` - Maximum norm.

**parr**: Parameter name that contains the result.

**normalize**

Normalization key; to be used only for vectors created by [[vec|*VEC]] :

- `YES` - Normalize the vector such that the norm is 1.0.
- `NO` - Do not normalize the vector (default).

## Notes

The NRM2 option corresponds to the Euclidian or L2 norm and is applicable to either vectors or matrices:

(equation omitted), (equation omitted)

(equation omitted), (equation omitted) where (equation omitted) is the complex conjugate of (equation omitted)

(equation omitted), (equation omitted) = largest eigenvalue of (equation omitted)

The NRM1 option corresponds to the L1 norm and is applicable to vectors and dense matrices:

(equation omitted) or (equation omitted), (equation omitted)

(equation omitted) or (equation omitted), (equation omitted)

The NRMINF option is the maximum norm and is applicable to either vectors or matrices:

(equation omitted) or (equation omitted), (equation omitted)

(equation omitted) or (equation omitted), (equation omitted)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NRM.html
