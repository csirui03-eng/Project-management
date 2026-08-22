---
apdl: "DETAB"
method: detab
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.set_up.SetUp.detab
generated: 2026-08-22
tags: [mapdl-command]
---

# DETAB

PyMAPDL: `mapdl.detab(elem='', lab='', v1='', v2='', v3='', v4='', v5='', v6='', **kwargs)`

Modifies element table results in the database.

## Parameters

**elem**: Element for which results are to be modified. If ALL, modify all selected elements ( [[esel|ESEL]] ) results. If `ELEM` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `ELEM`.

**lab**: Label identifying results. Valid labels are as defined with the [[etable|ETABLE]] command. Issue [[etable|ETABLE]], `STAT` to display labels and values.

**v1**, **v2**, **v3**, **v4**, **v5**, **v6**: Additional values (if any) assigned to consecutive element table columns.

## Notes

Modifies element table ( [[etable|ETABLE]] ) results in the database. For example, **DETAB** ,35,ABC,1000,2000,1000 assigns 1000, 2000, and 1000 to the first three table columns starting with label ABC for element 35. Use the [[pretab|PRETAB]] command to list the current results. After deleting a column of data using [[etable|ETABLE]], `Lab`,ERASE, the remaining columns of data are not shifted to compress the empty slot. Therefore, the user must allocate null (blank) values for `V1`, `V2`... `V6` for any ETABLE entries which have been deleted by issuing [[etable|ETABLE]], `Lab`,ERASE. All data are stored in the solution coordinate system but will be displayed in the results coordinate system ( [[rsys|RSYS]] ).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DETAB.html
