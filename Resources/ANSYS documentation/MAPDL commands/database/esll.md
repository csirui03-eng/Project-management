---
apdl: "ESLL"
method: esll
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.esll
generated: 2026-08-22
tags: [mapdl-command]
---

# ESLL

PyMAPDL: `mapdl.esll(type_='', **kwargs)`

Selects those elements associated with the selected lines.

## Parameters

**type_**

Label identifying the type of element select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

## Notes

Selects line elements belonging to meshed ( [[lmesh|LMESH]] ), selected ( [[lsel|LSEL]] ) lines.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESLL.html
