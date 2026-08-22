---
apdl: "BTOL"
method: btol
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.btol
generated: 2026-08-22
tags: [mapdl-command]
---

# BTOL

PyMAPDL: `mapdl.btol(ptol='', **kwargs)`

Specifies the Boolean operation tolerances.

**Command default:**

`PTOL` = 0.10E-4.

## Parameters

**ptol**: Point coincidence tolerance. Points within this distance to each other will be assumed to be coincident during Boolean operations. Loosening the tolerance will increase the run time and storage requirements, but will allow more Boolean intersections to succeed. Defaults to 0.10E-4.

## Notes

Use **BTOL**,DEFA to reset the setting to its default value. Use **BTOL**,STAT to list the status of the present setting.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BTOL.html
