---
apdl: "*LSENGINE"
method: lsengine
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.matrix_operations.MatrixOperations.lsengine
generated: 2026-08-22
tags: [mapdl-command]
---

# *LSENGINE

PyMAPDL: `mapdl.lsengine(type_='', enginename='', matrix='', option='', **kwargs)`

Creates a linear solver engine.

## Parameters

**type_**

Specifies the algorithm to be used:

- `DSS` - MKL sparse linear solver.
- `LAPACK` - LAPACK dense matrix linear solver (default if applied to dense matrices).
- `DSP` - Distributed sparse solver (default for sparse matrices).

**enginename**: Name used to identify this engine. Must be specified.

**matrix**: Name of the matrix to solve.

**option**

Option to control the memory mode of the DSS solver (used only if `Type` = DSS):

- `INCORE` - In-core memory mode.
- `OUTOFCORE` - Out-of-core memory mode.

## Notes

### Argument descriptions

- `type_ : str` - Specifies the algorithm to be used:
  - `DSS` - MKL sparse linear solver.
  - `LAPACK` - LAPACK dense matrix linear solver (default if applied to dense matrices).
  - `DSP` - Distributed sparse solver (default for sparse matrices).
- `enginename : str` - Name used to identify this engine. Must be specified.
- `matrix : str` - Name of the matrix to solve.

\* `option : str` - Option to control the memory mode of the DSS solver (used only if `Type` = DSS):

> - `INCORE` - In-core memory mode.
> - `OUTOFCORE` - Out-of-core memory mode.

This command creates a linear solver engine.

The DSS and DSP solvers can only be used with sparse matrices. For dense matrices, use the LAPACK solver.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSENGINE.html
