---
apdl: "LCFILE"
method: lcfile
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.lcfile
generated: 2026-08-22
tags: [mapdl-command]
---

# LCFILE

PyMAPDL: `mapdl.lcfile(lcno='', fname='', ext='', **kwargs)`

Creates a load case from an existing load case file.

## Parameters

**lcno**: Arbitrary (1-99) pointer number assigned to this load case.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to the `LCNO` value preceded by an L (for values 10-99) or by an L0 (for values 1-9).

## Notes

Creates a load case by establishing a pointer to an existing load case file ( [[lcwrite|LCWRITE]] ). This pointer ( `LCNO` ) can then be used on the [[lcase|LCASE]] or [[lcoper|LCOPER]] commands to read the load case data into the database. This command is typically used to reestablish load case pointers in a new Mechanical APDL session (pointers are not saved on the database file), or when more than one pointer to a single load case is desired. See the [[lcdef|LCDEF]] command for status and erase operations. See also [[lcdef|LCDEF]] to establish a pointer to a set of results on a results file (written during the analysis solution phase).

For details on using load case combination, see [Creating and Combining Load Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#bassummtlm51499325)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCFILE.html
