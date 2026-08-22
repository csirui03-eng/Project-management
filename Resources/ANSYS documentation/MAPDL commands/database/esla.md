---
apdl: "ESLA"
method: esla
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.esla
generated: 2026-08-22
tags: [mapdl-command]
---

# ESLA

PyMAPDL: `mapdl.esla(type_='', **kwargs)`

Selects those elements associated with the selected areas.

## Parameters

**type_**

Label identifying the type of element select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

## Notes

Selects area elements belonging to meshed ( [[amesh|AMESH]] ), selected ( [[asel|ASEL]] ) areas.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESLA.html
