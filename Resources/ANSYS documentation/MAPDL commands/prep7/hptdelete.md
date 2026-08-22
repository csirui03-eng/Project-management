---
apdl: "HPTDELETE"
method: hptdelete
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.hard_points.HardPoints.hptdelete
generated: 2026-08-22
tags: [mapdl-command]
---

# HPTDELETE

PyMAPDL: `mapdl.hptdelete(np1='', np2='', ninc='', **kwargs)`

Deletes selected hardpoints.

## Parameters

**np1**, **np2**, **ninc**: Delete the pattern of hard points beginning with `NP1` to `NP2` in steps of `NINC` (defaults to 1). If `NP1` = ALL, `NP2` and `NINC` are ignored and the pattern is all selected hard points ( [[ksel|KSEL]] ). If `NP1` = P, graphical picking is enabled and all remaining command fields are ignored.

## Notes

Deletes all attributes attached to the designated hard points as well as the hard points themselves. If any entity is attached to a designated hard point, the command detaches the hard point from that entity (the program will alert you that this will occur).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_HPTDELETE.html
