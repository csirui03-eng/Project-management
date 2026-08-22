---
apdl: "LCWRITE"
method: lcwrite
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.lcwrite
generated: 2026-08-22
tags: [mapdl-command]
---

# LCWRITE

PyMAPDL: `mapdl.lcwrite(lcno='', fname='', ext='', **kwargs)`

Creates a load case by writing results to a load case file.

## Parameters

**lcno**: Arbitrary pointer number (1-99) to be assigned to this load case.

**fname**: File name and directory path (248 characters maximum, including the characters needed for the directory path). An unspecified directory path defaults to the working directory; in this case, you can use all 248 characters for the file name. The file name defaults to `Jobname`.

**ext**: Filename extension (eight-character maximum). The extension defaults to the `LCNO` value preceded by an L (for values 10-99) or by an L0 (for values 1-9).

## Notes

Creates a load case by writing the results data in the database to a load case file. The database remains unchanged by this operation. A pointer is also established to the written set of results on the load case file. This pointer ( `LCNO` ) can then be used on the [[lcase|LCASE]] or [[lcoper|LCOPER]] commands to read the load case data into the database. By default, only summable results data (such as displacements, stresses, elastic strains) and constant results data (such as volume) are written to the load case file unless requested ( [[lcsum|LCSUM]] command). Non-summable results data (such as plastic strains, strain energy), boundary conditions, and nodal loads are not written to the load case file. The load case file may be named by default or by a user name. Rewriting to the same file overwrites the previous data. See the [[lcdef|LCDEF]] command for status and erase operations.

For details on using load case combination, see [Creating and Combining Load Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#bassummtlm51499325)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCWRITE.html
