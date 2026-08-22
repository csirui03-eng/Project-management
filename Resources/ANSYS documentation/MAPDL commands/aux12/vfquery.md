---
apdl: "VFQUERY"
method: vfquery
group: aux12
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux12.radiosity_solver.RadiositySolver.vfquery
generated: 2026-08-22
tags: [mapdl-command]
---

# VFQUERY

PyMAPDL: `mapdl.vfquery(srcelem='', tarelem='', **kwargs)`

Queries and prints element Hemicube view factors and average view factor.

## Parameters

**srcelem**: Elements representing the source radiating surfaces used to query the view factor at the target element(s). If `SRCELEM` = P, graphical picking is enabled (valid only in the GUI). If `SRCELEM` = ALL, all selected elements will have their view factors queried. A component name may also be substituted for `SRCELEM`. Selected elements must be flagged for surface to surface radiation in order to query view factors ( [[sf|SF]], [[sfa|SFA]], or [[sfe|SFE]] with Lab = RDSF). The view factors must have been previously computed.

**tarelem**: Element for view factor query. If `TARELEM` = P, graphical picking is enabled (valid only in the GUI). If `TARELEM` = ALL, all selected elements will have their view factors queried. A component name may also be substituted for `TARELEM`. Selected elements must be flagged for surface to surface radiation in order to query view factors ( [[sf|SF]], [[sfa|SFA]], or [[sfe|SFE]] with Lab = RDSF). The view factors must have been previously computed.

## Notes

View factors for each target element will be printed.

An average view factor for all target elements will be computed. (Use [[get|*GET]] to retrieve the average value).

When resuming a database, issue the command [[vfopt|VFOPT]],READ before issuing the **VFQUERY** command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VFQUERY.html
