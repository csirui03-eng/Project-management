---
apdl: "TBDELE"
method: tbdele
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tbdele
generated: 2026-08-22
tags: [mapdl-command]
---

# TBDELE

PyMAPDL: `mapdl.tbdele(lab='', mat1='', mat2='', inc='', tbopt='', **kwargs)`

Deletes previously defined material data tables.

## Parameters

**lab**: Material data table label to delete. (See [[tb|TB]] for valid `Lab` values.)

**mat1**, **mat2**, **inc**: Deletes data tables for materials `MAT1` to `MAT2` (default = `MAT1` ) in steps of `INC` (default = 1).

**tbopt**: Material data table option. (See [[tb|TB]] for valid `TBOPT` values for the given `Lab`.)

## Notes

If `Lab` = ALL, delete all material data tables.

If `MAT1` = ALL, `MAT2` and `INC` are ignored and all material data tables are deleted.

If `TBOPT` is specified, the material data table corresponding to `Lab` is deleted if it also has the specified table option. If `TBOPT` is not specified, all material data tables corresponding to `Lab` are deleted. `TBOPT` is ignored when `Lab` = ALL.

This command is also valid in SOLUTION, but is not intended for changing material behaviors between load steps.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBDELE.html
