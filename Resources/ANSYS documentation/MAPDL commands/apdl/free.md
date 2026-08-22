---
apdl: "*FREE"
method: free
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.free
generated: 2026-08-22
tags: [mapdl-command]
---

# *FREE

PyMAPDL: `mapdl.free(name='', val1='', **kwargs)`

Deletes a matrix or a solver object and frees its memory allocation.

## Parameters

**name**: Name of the matrix or solver object to delete. Use `Name` = ALL to delete all APDL Math matrices and solver objects. Use `Name` = WRK to delete all APDL Math matrices and solver objects that belong to a given workspace.

**val1**: If `Name` = WRK, `Val1` is the memory workspace number.

## Notes

### Argument descriptions

- `name : str` - Name of the matrix or solver object to delete. Use `Name` = ALL to delete all APDL Math matrices and solver objects. Use `Name` = WRK to delete all APDL Math matrices and solver objects that belong to a given workspace.
- `val1 : str` - If `Name` = WRK, `Val1` is the memory workspace number.

A [[clear|/CLEAR]] command will automatically delete all the current APDL Math objects.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FREE.html
