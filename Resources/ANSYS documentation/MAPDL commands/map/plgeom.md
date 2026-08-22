---
apdl: "PLGEOM"
method: plgeom
group: map
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.map.pressure_mapping.PressureMapping.plgeom
generated: 2026-08-22
tags: [mapdl-command]
---

# PLGEOM

PyMAPDL: `mapdl.plgeom(item='', nodekey='', **kwargs)`

Plots target and source geometries.

## Parameters

**item**

Items to plot:

- `BOTH` - Plot both target and source geometries (default).
- `TARGET` - Plot only the target geometry.
- `SOURCE` - Plot only the source geometry.

**nodekey**: If the source data contains faces (that is, surface elements were created upon the [[read|READ]] command), set `NODEkey` = 1 to plot only the source nodes rather than both the nodes and the elements.

## Notes

Target faces are displayed in gray and source points in yellow. If the source data contains faces (that is, surface elements were created upon the [[read|READ]] command), the source faces are also displayed in blue (unless `NODEkey` = 1), and both surfaces are made translucent.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLGEOM.html
