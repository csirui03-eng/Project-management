---
apdl: "*LSBAC"
method: lsbac
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.lsbac
generated: 2026-08-22
tags: [mapdl-command]
---

# *LSBAC

PyMAPDL: `mapdl.lsbac(enginename='', rhsvector='', solvector='', transkey='', **kwargs)`

Performs the solve (forward/backward substitution) of a factorized linear system.

## Parameters

**enginename**: Name used to identify this engine. Must have been previously created using [[lsengine|*LSENGINE]] and factorized using [[lsfactor|*LSFACTOR]].

**rhsvector**: Name of vector containing the right-hand side (load) vectors as input. Must have been previously defined as a [[vec|*VEC]] vector or a [[dmat|*DMAT]] matrix.

**solvector**: Name of vector that will contain the solution vectors upon completion. Must be predefined as a [[vec|*VEC]] vector or [[dmat|*DMAT]] matrix.

**transkey**: Transpose key. Set `TransKey` = TRANS to solve the transposed linear system. If blank, transpose will not be used.

## Notes

This command performs forward and back substitution to obtain the solution to the linear matrix equation Ax = b (or A <sup>T</sup> x = b if `TransKey` = TRANS). The matrix engine must have been previously defined using [[lsengine|*LSENGINE]], and the matrix factored using [[lsfactor|*LSFACTOR]].

You can use the [[dmat|*DMAT]],,,COPY (or [[vec|*VEC]],,,COPY) command to copy the load vector to the solution vector in order to predefine it with the appropriate size.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSBAC.html
