---
apdl: "VCROSS"
method: vcross
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.vcross
generated: 2026-08-22
tags: [mapdl-command]
---

# VCROSS

PyMAPDL: `mapdl.vcross(labxr='', labyr='', labzr='', labx1='', laby1='', labz1='', labx2='', laby2='', labz2='', **kwargs)`

Forms element table items from the cross product of two vectors.

## Parameters

**labxr**, **labyr**, **labzr**: Label assigned to X, Y, and Z-component of resultant vector.

**labx1**, **laby1**, **labz1**: X, Y, and Z-component of first vector label.

**labx2**, **laby2**, **labz2**: X, Y, and Z-component of second vector label.

## Notes

Forms labeled result items for the selected element from the cross product of two vectors:

{ `LabXR`, `LabYR`, `LabZR` } = { `LabX1`, `LabY1`, `LabZ1` } X { `LabX2`, `LabY2`, `LabZ2` }

Data must be in a consistent coordinate system. Labels are those associated with the [[etable|ETABLE]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VCROSS.html
