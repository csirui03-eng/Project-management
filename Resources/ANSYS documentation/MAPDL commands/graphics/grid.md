---
apdl: "/GRID"
method: grid
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.graphs.Graphs.grid
generated: 2026-08-22
tags: [mapdl-command]
---

# /GRID

PyMAPDL: `mapdl.grid(key='', **kwargs)`

Selects the type of grid on graph displays.

## Parameters

**key**

Grid key:

- `0 (OFF)` - No grid.
- `1 (ON)` - Full grid (X and Y grid lines).
- `2 (X)` - Partial grid (X grid lines only).
- `3 (Y)` - Partial grid (Y grid lines only)

## Notes

Selects the type of grid on graph displays. Graphs with multiple Y-axes can have multiple grids ( [[grtyp|/GRTYP]] ). The grid of the first curve is also used as the background grid (above and behind the curve). Grids for other curves are limited to be under the curves. See also [[gthk|/GTHK]] and [[gropt|/GROPT]] for other grid options.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GRID.html
