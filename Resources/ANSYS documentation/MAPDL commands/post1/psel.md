---
apdl: "PSEL"
method: psel
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.psel
generated: 2026-08-22
tags: [mapdl-command]
---

# PSEL

PyMAPDL: `mapdl.psel(type_='', pname1='', pname2='', pname3='', pname4='', pname5='', pname6='', pname7='', pname8='', pname9='', pname10='', **kwargs)`

Selects a path or paths.

## Parameters

**type_**

Label identifying the type of select:

- `S` - Select a new path.
- `R` - Reselect a path from the current set of paths.
- `A` - Additionally select a path and extend the current set of paths.
- `U` - Unselect a path from the current set of paths.
- `ALL` - Restore the full set of paths.
- `NONE` - Unselect the full set of paths.
- `INV` - Invert the current set of paths (selected becomes unselected and vice versa).

**pname1**, **pname2**, **pname3**, **pname4**, **pname5**, **pname6**, **pname7**, **pname8**, **pname9**, **pname10**: Name of existing path(s).

## Notes

Selects a path or multiple paths, up to ten. Data are flagged as selected and unselected; no data are actually deleted from the database. There is no default for this command; you must specify a type and pathname.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PSEL.html
