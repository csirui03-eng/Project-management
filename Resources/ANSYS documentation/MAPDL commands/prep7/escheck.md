---
apdl: "ESCHECK"
method: escheck
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.database.Database.escheck
generated: 2026-08-22
tags: [mapdl-command]
---

# ESCHECK

PyMAPDL: `mapdl.escheck(sele='', levl='', defkey='', **kwargs)`

Perform element shape checking for a selected element set.

## Parameters

**sele**

Specifies whether to select elements for checking:

- `(blank)` - List all warnings/errors from element shape checking.
- `ESEL` - Select the elements based on the. `Levl` criteria specified below.

**levl**

- `WARN` - Select elements producing warning and error messages.
- `ERR` - Select only elements producing error messages (default).

**defkey**

Specifies whether check should be performed on deformed element shapes.

- `0` - Do not update node coordinates before performing shape checks (default).
- `1` - Update node coordinates using the current set of deformations in the database.

## Notes

Shape checking will occur according to the current [[shpp|SHPP]] settings. Although **ESCHECK** is valid in all processors, `Defkey` uses the current results in the database. If no results are available a warning will be issued.

This command is also valid in PREP7, SOLUTION and POST1.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESCHECK.html
