---
apdl: "LCASE"
method: lcase
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.load_case_calculations.LoadCaseCalculations.lcase
generated: 2026-08-22
tags: [mapdl-command]
---

# LCASE

PyMAPDL: `mapdl.lcase(lcno='', **kwargs)`

Reads a load case into the database.

## Parameters

**lcno**: Load case pointer number ( [[lcdef|LCDEF]],STAT). Defaults to 1.

## Notes

Reads a load case into the database. Load cases are created as described on the [[lcdef|LCDEF]] or [[lcwrite|LCWRITE]] commands. The results portion of the database and the applied forces and displacements are cleared before reading the data in. Absolute values ( [[lcabs|LCABS]] ) and scale factors ( [[lcfact|LCFACT]] ) can be applied during the read operation.

For details on using load case combination, see [Creating and Combining Load Cases](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_4.html#bassummtlm51499325)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCASE.html
