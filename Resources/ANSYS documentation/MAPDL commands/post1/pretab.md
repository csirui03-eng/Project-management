---
apdl: "PRETAB"
method: pretab
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.element_table.ElementTable.pretab
generated: 2026-08-22
tags: [mapdl-command]
---

# PRETAB

PyMAPDL: `mapdl.pretab(lab1='', lab2='', lab3='', lab4='', lab5='', lab6='', lab7='', lab8='', lab9='', **kwargs)`

Prints the element table items.

## Parameters

**lab1**, **lab2**, **lab3**, **lab4**, **lab5**, **lab6**, **lab7**, **lab8**, **lab9**: Print selected items. Valid labels are (blank) or any label as specified with the [[etable|ETABLE]] command. Convenience labels may be used for `Lab1` to select groups of labels (10 labels maximum): GRP1 for first 10 stored items; GRP2 for items 11 to 20; GRP3 for items 21 to 30; GRP4 for items 31 to 40; GRP5 for items 41 to 50. Enter [[etable|ETABLE]],STAT command to list stored item order. If all labels are blank, print first 10 stored items (GRP1).

## Notes

Prints the items stored in the table defined with the [[etable|ETABLE]] command. Item values will be listed for the selected elements in the sorted sequence ( [[esort|ESORT]] ). The [[force|FORCE]] command can be used to define which component of the nodal load is to be used (static, damping, inertia, or total).

Portions of this command are not supported by PowerGraphics ( [[graphics|/GRAPHICS]],POWER).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PRETAB.html
