---
apdl: "SFALIST"
method: sfalist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_surface_loads.SolidSurfaceLoads.sfalist
generated: 2026-08-22
tags: [mapdl-command]
---

# SFALIST

PyMAPDL: `mapdl.sfalist(area='', lab='', **kwargs)`

Lists the surface loads for the specified area.

## Parameters

**area**: Area at which surface load is to be listed. If ALL (or blank), list for all selected areas ( [[asel|ASEL]] ). If `AREA` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `AREA`.

**lab**: Valid surface load label. If ALL (or blank), use all appropriate labels. See the [[sfa|SFA]] command for labels.

## Notes

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFALIST.html
