---
apdl: "*VLEN"
method: vlen
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vlen
generated: 2026-08-22
tags: [mapdl-command]
---

# *VLEN

PyMAPDL: `mapdl.vlen(nrow='', ninc='', **kwargs)`

Specifies the number of rows to be used in array parameter operations.

## Parameters

**nrow**: Number of rows to be used with the **\*V** `XX` or **\*M** `XX` operations. Defaults to the number of rows needed to fill the result array.

**ninc**: Perform the operation on every `NINC` row (defaults to 1).

## Notes

### Argument descriptions

\* `nrow : str` - Number of rows to be used with the **\*V** `XX` or **\*M** `XX` operations. Defaults to the number of rows needed to fill the result array.

- `ninc : str` - Perform the operation on every `NINC` row (defaults to 1).

Specifies the number of rows to be used in array parameter operations. The size of the submatrix used is determined from the upper left starting array element (defined on the operation command) to the lower right array element (defined by the number of rows on this command and the number of columns on the [[vcol|*VCOL]] command). `NINC` allows skipping row operations for some operation commands. Skipped rows are included in the row count. The starting row number must be defined on the operation command for each parameter read and for the result written.

The default `NROW` is calculated from the maximum number of rows of the result array (the [[dim|*DIM]] row dimension) minus the starting location + 1. For example, [[dim|*DIM]],R,,10 and a starting location of R(7) gives a default of 4 loops (filling R(7), R(8), R(9), and R(10)). Repeat operations automatically terminate at the last row of the result array. Existing values in the rows and columns of the results matrix remain unchanged where not overwritten by the requested input or operation values.

The stride ( `NINC` ) allows operations to be performed at regular intervals. It has no effect on the total number of row operations. Skipped operations retain the previous result. For example, [[dim|*DIM]],R,,6, with a starting location of R(1), `NROW` = 10, and `NINC` = 2 calculates values for locations R(1), R(3), and R(5) and retains values for locations R(2), R(4), and R(6). A more general skip control may be done by masking ( [[vmask|*VMASK]] ). The row control settings are reset to the defaults after each **\*V** `XX` or **\*M** `XX` operation. Use [[vstat|*VSTAT]] to list settings.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VLEN.html
