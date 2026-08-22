---
apdl: "SFADELE"
method: sfadele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_surface_loads.SolidSurfaceLoads.sfadele
generated: 2026-08-22
tags: [mapdl-command]
---

# SFADELE

PyMAPDL: `mapdl.sfadele(area='', lkey='', lab='', **kwargs)`

Deletes surface loads from areas.

## Parameters

**area**: Area to which surface load deletion applies. If ALL, delete load from all selected areas ( [[asel|ASEL]] ). If `AREA` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `AREA`.

**lkey**: Load key associated with surface load (defaults to 1). See the [[sfa|SFA]] command for details.

**lab**: Valid surface load label. If ALL, use all appropriate labels. See the [[sfa|SFA]] command for labels.

## Notes

Deletes surface loads (and all corresponding finite element loads) from selected areas.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFADELE.html
