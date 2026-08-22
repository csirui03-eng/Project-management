---
apdl: "ASLL"
method: asll
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.selecting.Selecting.asll
generated: 2026-08-22
tags: [mapdl-command]
---

# ASLL

PyMAPDL: `mapdl.asll(type_='', arkey='', **kwargs)`

Selects those areas containing the selected lines.

## Parameters

**type_**

Label identifying the type of area select:

- `S` - Select a new set (default).
- `R` - Reselect a set from the current set.
- `A` - Additionally select a set and extend the current set.
- `U` - Unselect a set from the current set.

**arkey**

Specifies whether all contained area lines must be selected ( [[lsel|LSEL]] ):

- `0` - Select area if any of its lines are in the selected line set.
- `1` - Select area only if all of its lines are in the selected line set.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ASLL.html
