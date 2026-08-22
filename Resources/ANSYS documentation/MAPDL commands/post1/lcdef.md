---
apdl: "LCDEF"
method: lcdef
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.lcdef
generated: 2026-08-22
tags: [mapdl-command]
---

# LCDEF

PyMAPDL: `mapdl.lcdef(lcno='', lstep='', sbstep='', kimg='', **kwargs)`

Creates a load case from a set of results on a results file.

## Parameters

**lcno**: Arbitrary pointer number (1-99) to be assigned to the load case specified by `LSTEP`, `SBSTEP` and by the [[file|FILE]] command. Defaults to 1 + previous value.

**lstep**: Load step number to be defined as the load case. Defaults to one.

**sbstep**: Substep number. Defaults to the last substep of the load step.

**kimg**

Used only with results from complex analyses:

- `0` - Use real part of complex solution
- `1` - Use imaginary part.

## Notes

Creates a load case by establishing a pointer to a set of results on a results file (written during the analysis solution phase). This pointer ( `LCNO` ) can then be used on the [[lcase|LCASE]] or [[lcoper|LCOPER]] commands to read the load case data into the database.

Issue **LCDEF**,ERASE to delete all load case pointers (and all load case files, if any). Issue **LCDEF**, `LCNO`,ERASE to delete only the specific load case pointer `LCNO` (and its file, if any). With the ERASE options, all pointers are deleted; however only files with the default extension ( [[lcwrite|LCWRITE]] ) are deleted. Issue **LCDEF**,STAT for status of all selected load cases ( [[lcsel|LCSEL]] ), or **LCDEF**,STAT,ALL for status of all load cases. The [[stat|STAT]] command may be used to list all load cases. See also [[lcfile|LCFILE]] to establish a pointer to a set of results on a load case file (written by [[lcwrite|LCWRITE]] ). Harmonic element data read from a result file load case is stored at the zero-degree position.

For details on using load case combination, see [Creating and Combining Load Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#bassummtlm51499325)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCDEF.html
