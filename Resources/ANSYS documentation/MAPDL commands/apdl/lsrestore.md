---
apdl: "*LSRESTORE"
method: lsrestore
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.lsrestore
generated: 2026-08-22
tags: [mapdl-command]
---

# *LSRESTORE

PyMAPDL: `mapdl.lsrestore(enginename='', filename='', **kwargs)`

Restores a linear solver engine from a binary file.

## Parameters

**enginename**: Name used to identify this engine.

**filename**: Name of the file to read from.

## Notes

### Argument descriptions

- `enginename : str` - Name used to identify this engine.
- `filename : str` - Name of the file to read from.

Restores a previously dumped Linear Solver (see the [[lsdump|*LSDUMP]] command). This Linear Solver can be used to solve a linear system using the [[lsbac|*LSBAC]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSRESTORE.html
