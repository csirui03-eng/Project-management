---
apdl: "*COMP"
method: comp
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.comp
generated: 2026-08-22
tags: [mapdl-command]
---

# *COMP

PyMAPDL: `mapdl.comp(matrix='', algorithm='', threshold='', val1='', val2='', **kwargs)`

Compresses a matrix using a specified algorithm.

## Parameters

**matrix**: Name of the matrix to compress.

**algorithm**

Algorithm or method to use:

- `SVD` - Singular value decomposition algorithm (default).
- `MGS` - Modified Gram-Schmidt algorithm.
- `SPARSE` - Compress a sparse matrix based on the threshold value.

**threshold**: Numerical threshold value used to manage the compression. The default value depends on the method of compression: 1E-7 for SVD; 1E-14 for MGS; 1E-16 for SPARSE.

**val1**: Name of the vector used to store the (equation omitted) values (see [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_COMP.html#eq11850956-35ca-43ce-a803-b83b50b4d2af) below). This argument is optional.

**val2**: Name of the dense matrix used to store the (equation omitted) output matrix (see [Notes](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_cmd/Hlp_C_COMP.html#eq11850956-35ca-43ce-a803-b83b50b4d2af) below). This argument is optional.

## Notes

The SVD and MGS algorithms are only applicable to dense matrices that were created using the [[dmat|*DMAT]] command. Columns that are linearly dependent on others are removed, leaving the independent or basis vectors. The matrix is resized according to the new size determined by the algorithm.

For the SVD algorithm, the singular value decomposition of an input matrix (equation omitted) is a factorization of the form:

(equation not available in the PyMAPDL source, see the Ansys help page)

Here, the (equation omitted) matrix is replaced by the (equation omitted) matrix, according to the specified threshold.

The SPARSE compression method is only applicable to sparse matrices that were created using the [[smat|*SMAT]] command. All terms that have an absolute value below the specified threshold, relative to the maximum value in the matrix, are removed from the original matrix. For example, given a sparse matrix having 100 as the largest term and `THRESHOLD` = 0.5, all terms having an absolute value below 0.5\*100 = 50 are removed.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_COMP.html
