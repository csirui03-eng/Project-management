---
apdl: "*HPROD"
method: hprod
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.hprod
generated: 2026-08-22
tags: [mapdl-command]
---

# *HPROD

PyMAPDL: `mapdl.hprod(a='', b='', c='', **kwargs)`

Performs a Hadamard vector product (C = A∘B).

## Parameters

**a**: Name of vector A. Must have been previously created by a [[vec|*VEC]] command.

**b**: Name of vector B. Must have been previously created by a [[vec|*VEC]] command.

**c**: Name of vector C. Must be specified (no default).

## Notes

For two vectors `A` and `B` of the same dimension `n`, the Hadamard product (A∘B) is a vector of the same dimension as the operands, with elements given by:

(equation not available in the PyMAPDL source, see the Ansys help page)

This command is limited to vector operands.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HPROD.html
