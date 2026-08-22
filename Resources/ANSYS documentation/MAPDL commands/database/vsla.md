---
apdl: "VSLA"
method: vsla
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.vsla
generated: 2026-08-22
tags: [mapdl-command]
---

# VSLA

PyMAPDL: `mapdl.vsla(type_='', vlkey='', **kwargs)`

Selects those volumes containing the selected areas.

## Parameters

**type_**

Label identifying the type of volume select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

**vlkey**

Specifies whether all contained volume areas must be selected ( [[asel|ASEL]] ):

- `0` - Select volume if any of its areas are in the selected area set.
- `1` - Select volume only if all of its areas are in the selected area set.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VSLA.html
