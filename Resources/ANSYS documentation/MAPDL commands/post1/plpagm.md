---
apdl: "PLPAGM"
method: plpagm
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.path_operations.PathOperations.plpagm
generated: 2026-08-22
tags: [mapdl-command]
---

# PLPAGM

PyMAPDL: `mapdl.plpagm(item='', gscale='', nopt='', **kwargs)`

Displays path items along the path geometry.

## Parameters

**item**: The path data item to be displayed on the currently active path (defined by the [[path|PATH]] command). Valid path items are those defined with the [[pdef|PDEF]] or [[plnear|PLNEAR]] commands.

**gscale**: Scale factor for the offset from the path for the path data item displays. Defaults to 1.0.

**nopt**

Determines how data is displayed:

- `(blank)` - Do not display nodes, and scale the display based on the currently selected node set (default).
- `NODE` - Display path item data along with the currently selected set of nodes. The display geometry is scaled to the selected node set.

## Notes

You can use the `Gscale` argument to scale the contour display offset from the path for clarity. You need to type all six characters to issue this command.

Fore more information, see [Mapping Results onto a Path](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_bas/Hlp_G_BAS5_3.html#basdelepathtlm51799)

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLPAGM.html
