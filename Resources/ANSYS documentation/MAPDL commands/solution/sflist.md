---
apdl: "SFLIST"
method: sflist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sflist
generated: 2026-08-22
tags: [mapdl-command]
---

# SFLIST

PyMAPDL: `mapdl.sflist(node='', lab='', **kwargs)`

Lists surface loads.

## Parameters

**node**: Node at which surface load is to be listed. If ALL (or blank), list for all selected nodes ( [[nsel|NSEL]] ). If `NODE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `NODE`.

**lab**: Valid surface load label. If ALL (or blank), use all appropriate labels. See the [[sf|SF]] command for labels

## Notes

Lists the surface loads as applied with the [[sf|SF]] command. Loads are listed only for the specified nodes on external faces of selected area and volume elements. Use [[sfelist|SFELIST]] for line elements. The surface loads listed correspond to the current database values. The database is not updated for surface loads in POST1. Surface loads specified in tabular form, however, do list their values corresponding to the current results set in POST1.

For `SURF151` or `SURF152` elements with an extra node for radiation and/or convection calculations (KEYOPT(5) = 1), the bulk temperature listed is the temperature of the extra node. If the thermal solution does not converge, the extra node temperature is not available for listing.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFLIST.html
