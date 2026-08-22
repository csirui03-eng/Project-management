---
apdl: "TBLIST"
method: tblist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.data_tables.DataTables.tblist
generated: 2026-08-22
tags: [mapdl-command]
---

# TBLIST

PyMAPDL: `mapdl.tblist(lab='', mat='', **kwargs)`

Lists the material data tables.

## Parameters

**lab**: Data table label. (See the [[tb|TB]] command for valid labels.) Defaults to the active table. If ALL, list data for all labels.

**mat**: Material number to be listed (defaults to the active material). If ALL, list data tables for all materials.

## Notes

This command is a utility command, valid anywhere.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TBLIST.html
