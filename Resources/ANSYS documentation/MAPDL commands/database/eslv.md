---
apdl: "ESLV"
method: eslv
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.eslv
generated: 2026-08-22
tags: [mapdl-command]
---

# ESLV

PyMAPDL: `mapdl.eslv(type_='', **kwargs)`

Selects elements associated with the selected volumes.

## Parameters

**type_**

Label identifying the type of element selected:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

## Notes

Selects volume elements belonging to meshed ( [[vmesh|VMESH]] ), selected ( [[vsel|VSEL]] ) volumes.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESLV.html
