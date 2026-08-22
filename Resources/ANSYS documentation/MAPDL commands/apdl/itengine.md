---
apdl: "*ITENGINE"
method: itengine
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.itengine
generated: 2026-08-22
tags: [mapdl-command]
---

# *ITENGINE

PyMAPDL: `mapdl.itengine(type_='', enginename='', precondname='', matrix='', rhsvector='', solvector='', maxiter='', toler='', **kwargs)`

Performs a solution using an iterative solver.

## Parameters

**type_**

Specifies the algorithm to be used:

- `PCG` - Preconditioned conjugate gradient (default).

**enginename**: Name used to identify this iterative solver engine. Must be specified.

**precondname**: Linear solver engine name ( [[lsengine|*LSENGINE]] ) identifying the factored matrix to be used as the preconditioner.

**matrix**: Name of the matrix to solve.

**rhsvector**: Matrix (load vector) name.

**solvector**: Solution vector name. If non-zero, it will be taken as the initial vector for the iterative process.

**maxiter**: Maximum number of iterations allowed. Default is 2 times the number of rows in the matrix.

**toler**: Convergence tolerance. Default is 1.0E-8.

## Notes

This command solves Ax = b using a preconditioned conjugate gradient algorithm. It uses an existing factored system as the preconditioner. This solution method is useful if an existing matrix has been solved and minor changes have been made to the matrix.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ITENGINE.html
