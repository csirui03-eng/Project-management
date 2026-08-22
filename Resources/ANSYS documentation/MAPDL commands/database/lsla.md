---
apdl: "LSLA"
method: lsla
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.lsla
generated: 2026-08-22
tags: [mapdl-command]
---

# LSLA

PyMAPDL: `mapdl.lsla(type_='', **kwargs)`

Selects those lines contained in the selected areas.

## Parameters

**type_**

Label identifying the type of line select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSLA.html
