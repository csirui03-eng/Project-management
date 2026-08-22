---
apdl: "SUSEL"
method: susel
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.susel
generated: 2026-08-22
tags: [mapdl-command]
---

# SUSEL

PyMAPDL: `mapdl.susel(type_='', name1='', name2='', name3='', name4='', name5='', name6='', name7='', name8='', **kwargs)`

Selects a subset of surfaces

## Parameters

**type_**

Label identifying the type of select:

- `S` - Selects a new set (default).
- `R` - Reselects a set from the current set.
- `A` - Additionally selects a set and extends the current set.
- `U` - Unselects a set from the current set.
- `ALL` - Also selects all surfaces.
- `NONE` - Unselects all surfaces.

**name1**, **name2**, **name3**, **name4**, **name5**, **name6**, **name7**, **name8**: Eight character surface names

## Notes

The selected set of surfaces is used in the following operations: [[sumap|SUMAP]], [[sudel|SUDEL]], [[sucalc|SUCALC]], [[sueval|SUEVAL]], and [[suvect|SUVECT]].

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUSEL.html
