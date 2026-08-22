---
apdl: "PLMAP"
method: plmap
group: map
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.map.pressure_mapping.PressureMapping.plmap
generated: 2026-08-22
tags: [mapdl-command]
---

# PLMAP

PyMAPDL: `mapdl.plmap(item='', nodekey='', imagkey='', **kwargs)`

Plots target and source pressures.

## Parameters

**item**

Items to plot:

- `BOTH` - Plot both target and source pressures (default).
- `TARGET` - Plot only the target pressures.
- `SOURCE` - Plot only the source pressures.

**nodekey**: If the source data contains faces (that is, surface elements were created upon the [[read|READ]] command), set `NODEkey` = 1 to plot only the source nodes rather than both the nodes and the elements.

**imagkey**

- `0` - Plot the real pressures (default).
- `1` - Plot the imaginary pressures.

## Notes

Pressures on the target faces are displayed as a color contour plot using the command [[psf|/PSF]] ,PRES,,3. If the source data contains faces (that is, surface elements were created upon the [[read|READ]] command), the source faces are also displayed using a color contour plot by default. If `NODEkey` = 1 or no source faces are available, the source pressures are displayed as colored node symbols ( [[psymb|/PSYMB]],DOT,1 command).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PLMAP.html
