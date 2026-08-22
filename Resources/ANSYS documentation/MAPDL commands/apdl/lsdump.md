---
apdl: "*LSDUMP"
method: lsdump
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.lsdump
generated: 2026-08-22
tags: [mapdl-command]
---

# *LSDUMP

PyMAPDL: `mapdl.lsdump(enginename='', filename='', **kwargs)`

Dumps a linear solver engine to a binary File.

## Parameters

**enginename**: Name used to identify this engine. Must have been previously created using [[lsengine|*LSENGINE]] and factorized using [[lsfactor|*LSFACTOR]].

**filename**: Name of the file to create.

## Notes

### Argument descriptions

- `enginename : str` - Name used to identify this engine. Must have been previously created using [[lsengine|*LSENGINE]] and factorized using [[lsfactor|*LSFACTOR]].
- `filename : str` - Name of the file to create.

Dumps a previously factorized linear solver system to a binary file. Only LAPACK and BCS linear solvers can be used with this feature. The Linear Solver can later be restored with the [[lsrestore|*LSRESTORE]] command.

A BCS Sparse Solver can be dumped only if uses the `INCORE` memory option (see [[bcsoption|BCSOPTION]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSDUMP.html
