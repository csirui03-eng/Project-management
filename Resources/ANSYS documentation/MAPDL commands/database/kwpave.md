---
apdl: "KWPAVE"
method: kwpave
group: database
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.database.working_plane.WorkingPlane.kwpave
generated: 2026-08-22
tags: [mapdl-command]
---

# KWPAVE

PyMAPDL: `mapdl.kwpave(p1='', p2='', p3='', p4='', p5='', p6='', p7='', p8='', p9='', **kwargs)`

Moves the working plane origin to the average location of keypoints.

## Parameters

**p1**, **p2**, **p3**, **p4**, **p5**, **p6**, **p7**, **p8**, **p9**: Keypoints used in calculation of the average. At least one must be defined. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

## Notes

Moves the origin of the working plane to the average of the specified keypoints. Averaging is based on the active coordinate system.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KWPAVE.html
