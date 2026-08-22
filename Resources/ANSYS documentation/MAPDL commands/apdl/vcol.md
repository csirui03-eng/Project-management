---
apdl: "*VCOL"
method: vcol
group: apdl
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.apdl.array_parameters.ArrayParameters.vcol
generated: 2026-08-22
tags: [mapdl-command]
---

# *VCOL

PyMAPDL: `mapdl.vcol(ncol1='', ncol2='', **kwargs)`

Specifies the number of columns in matrix operations.

## Parameters

**ncol1**: Number of columns to be used for Par1 with **\*M** `XX` operations. Defaults to whatever is needed to fill the result array.

**ncol2**: Number of columns to be used for Par2 with **\*M** `XX` operations. Defaults to whatever is needed to fill the result array.

## Notes

### Argument descriptions

\* `ncol1 : str` - Number of columns to be used for Par1 with **\*M** `XX` operations. Defaults to whatever is needed to fill the result array.

\* `ncol2 : str` - Number of columns to be used for Par2 with **\*M** `XX` operations. Defaults to whatever is needed to fill the result array.

Specifies the number of columns to be used in array parameter matrix operations. The size of the submatrix used is determined from the upper left starting array element (defined on the operation command) to the lower right array element (defined by the number of columns on this command and the number of rows on the [[vlen|*VLEN]] command).

The default `NCOL` is calculated from the maximum number of columns of the result array (the [[dim|*DIM]] column dimension) minus the starting location + 1. For example, [[dim|*DIM]],R,,1,10 and a starting location of R(1,7) gives a default of 4 columns ( starting with R(1,7), R(1,8), R(1,9), and R(1,10)). Repeat operations automatically terminate at the last column of the result array. Existing values in the rows and columns of the results matrix remain unchanged where not overwritten by the requested input or operation values.

The column control settings are reset to the defaults after each **\*M** `XX` operation. Use [[vstat|*VSTAT]] to list settings.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VCOL.html
