---
apdl: "VDOT"
method: vdot
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.vdot
generated: 2026-08-22
tags: [mapdl-command]
---

# VDOT

PyMAPDL: `mapdl.vdot(labr='', labx1='', laby1='', labz1='', labx2='', laby2='', labz2='', **kwargs)`

Forms an element table item from the dot product of two vectors.

## Parameters

**labr**: Label assigned to dot product result.

**labx1**, **laby1**, **labz1**: X, Y, and Z-component of first vector label.

**labx2**, **laby2**, **labz2**: X, Y, and Z-component of second vector label.

## Notes

Forms labeled result items for the selected element from the dot product of two vectors:

`LabR` = { `LabX1`, `LabY1`, `LabZ1` } { `LabX2`, `LabY2`, `LabZ2` }

Data must be in a consistent coordinate system. Labels are those associated with the [[etable|ETABLE]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VDOT.html
