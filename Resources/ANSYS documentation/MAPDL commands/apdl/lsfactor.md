---
apdl: "*LSFACTOR"
method: lsfactor
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.lsfactor
generated: 2026-08-22
tags: [mapdl-command]
---

# *LSFACTOR

PyMAPDL: `mapdl.lsfactor(enginename='', option='', **kwargs)`

Performs the numerical factorization of a linear solver system.

## Parameters

**enginename**: Name used to identify this engine. Must have been previously created using [[lsengine|*LSENGINE]].

**option**

Option to invert the matrix, used only with an LAPACK engine ( [[lsengine|*LSENGINE]],LAPACK):

- `INVERT` - Invert the matrix.

## Notes

Performs the computationally intensive, memory intensive factorization of a matrix specified by [[lsengine|*LSENGINE]], using the solver engine also specified by [[lsengine|*LSENGINE]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSFACTOR.html
