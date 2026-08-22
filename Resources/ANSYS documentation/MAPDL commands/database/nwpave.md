---
apdl: "NWPAVE"
method: nwpave
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.nwpave
generated: 2026-08-22
tags: [mapdl-command]
---

# NWPAVE

PyMAPDL: `mapdl.nwpave(n1='', n2='', n3='', n4='', n5='', n6='', n7='', n8='', n9='', **kwargs)`

Moves the working plane origin to the average location of nodes.

## Parameters

**n1**, **n2**, **n3**, **n4**, **n5**, **n6**, **n7**, **n8**, **n9**: Nodes used in calculation of the average. At least one must be defined. If `N1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

## Notes

Averaging is based on the active coordinate system.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NWPAVE.html
