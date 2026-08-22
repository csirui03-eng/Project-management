---
apdl: "SFLLIST"
method: sfllist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_surface_loads.SolidSurfaceLoads.sfllist
generated: 2026-08-22
tags: [mapdl-command]
---

# SFLLIST

PyMAPDL: `mapdl.sfllist(line='', lab='', **kwargs)`

Lists the surface loads for lines.

## Parameters

**line**: Line at which surface load is to be listed. If ALL (or blank), list for all selected lines ( [[lsel|LSEL]] ). If `LINE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `LINE`.

**lab**: Valid surface load label. If ALL (or blank), use all appropriate labels. See the [[sfl|SFL]] command for labels.

## Notes

Lists the surface loads for the specified line.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFLLIST.html
