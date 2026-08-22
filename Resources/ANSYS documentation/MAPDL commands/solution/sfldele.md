---
apdl: "SFLDELE"
method: sfldele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_surface_loads.SolidSurfaceLoads.sfldele
generated: 2026-08-22
tags: [mapdl-command]
---

# SFLDELE

PyMAPDL: `mapdl.sfldele(line='', lab='', **kwargs)`

Deletes surface loads from lines.

## Parameters

**line**: Line to which surface load deletion applies. If ALL, delete load from all selected lines ( [[lsel|LSEL]] ). If `LINE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `LINE`.

**lab**: Valid surface load label. If ALL, use all appropriate labels. See the [[sfl|SFL]] command for labels.

## Notes

Deletes surface loads (and all corresponding finite element loads) from selected lines.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFLDELE.html
