---
apdl: "*EIGEN"
method: eigen
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.eigen
generated: 2026-08-22
tags: [mapdl-command]
---

# *EIGEN

PyMAPDL: `mapdl.eigen(kmatrix='', mmatrix='', cmatrix='', evals='', evects='', **kwargs)`

Performs a modal solution with unsymmetric or damping matrices.

## Parameters

**kmatrix**: Name of the stiffness matrix. May be a real or complex-valued matrix.

**mmatrix**: Name of the mass matrix.

**cmatrix**: Name of the damping matrix (used only for [[modopt|MODOPT]],DAMP).

**evals**: Name of the output eigenvalues vector. It will be an `m` -long [[vec|*VEC]] vector of complex values, where `m` is the number of eigenvalues requested ( [[modopt|MODOPT]] ).

**evects**: Name of the output eigenvector matrix. It will be a `n` x `m` [[dmat|*DMAT]] (dense) matrix of complex values, where `n` is the size of the matrix and `m` is the number of eigenvalues requested ( [[modopt|MODOPT]] ).

## Notes

Use the command [[antype|ANTYPE]],MODAL and the [[modopt|MODOPT]] command to specify the modal solution options. Only [[modopt|MODOPT]] ,DAMP, [[modopt|MODOPT]],UNSYM, [[modopt|MODOPT]],LANB, and [[modopt|MODOPT]],SUBSP are supported.

**\*EIGEN** with Block Lanczos (LANB) only supports sparse matrices. Distributed-Memory Parallel (DMP) Restriction This command is not supported in a DMP solution.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EIGEN.html
