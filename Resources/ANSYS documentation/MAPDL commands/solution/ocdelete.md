---
apdl: "OCDELETE"
method: ocdelete
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.ocean.Ocean.ocdelete
generated: 2026-08-22
tags: [mapdl-command]
---

# OCDELETE

PyMAPDL: `mapdl.ocdelete(datatype='', zonename='', **kwargs)`

Deletes a previously defined ocean load.

## Parameters

**datatype**

Ocean data type to delete. Valid values are BASIC, CURRENT, WAVE, ZONE, and ALL.

For `DataType` = ALL, all defined ocean loads are deleted.

**zonename**: The name of the ocean zone to delete. If no name is specified, all defined ocean zones are deleted. Valid only when DataType = ZONE.

## Notes

The **OCDELETE** command deletes previously specified ocean data from the database.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_OCDELETE.html
