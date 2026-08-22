---
apdl: "SFELIST"
method: sfelist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sfelist
generated: 2026-08-22
tags: [mapdl-command]
---

# SFELIST

PyMAPDL: `mapdl.sfelist(elem='', lab='', **kwargs)`

Lists the surface loads for elements.

## Parameters

**elem**: Element at which surface load is to be listed. If ALL (or blank), list loads for all selected elements ( [[esel|ESEL]] ). If `ELEM` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `ELEM`.

**lab**: Valid surface load label. If ALL (or blank), use all appropriate labels. See the [[sfe|SFE]] command for labels.

## Notes

The surface loads listed correspond to the current database values. The database is not updated for surface loads in POST1. Surface loads specified in tabular form, however, do list their values corresponding to the current results set in POST1.

For `SURF151` or `SURF152` elements with an extra node for radiation and/or convection calculations (KEYOPT(5) = 1), the bulk temperature listed is the temperature of the extra node. If the thermal solution does not converge, the extra node temperature is not available for listing.

Film effectiveness and free stream temperatures specified by the [[sfe|SFE]] command ( `Lab` = CONV) can only be listed by this command. The command lists film coefficients and bulk temperatures first and then film effectiveness and free stream temperatures below those values.

Distributed-Memory Parallel (DMP) Restriction In a DMP analysis within the SOLUTION processor, **SFELIST** support is not available for elements `SURF151` and `SURF152` when surface loading is applied via extra nodes (KEYOPT(5 \> 0). If the command is issued under these circumstances, the resulting surface loads shown are not reliable.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFELIST.html
