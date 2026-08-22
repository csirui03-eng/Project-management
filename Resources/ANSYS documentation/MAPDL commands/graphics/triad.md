---
apdl: "/TRIAD"
method: triad
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.triad
generated: 2026-08-22
tags: [mapdl-command]
---

# /TRIAD

PyMAPDL: `mapdl.triad(lab='', **kwargs)`

Shows the global XYZ coordinate triad on displays.

## Parameters

**lab**

Display triad as follows:

- `ORIG` - Display triad at global origin (default).
- `OFF` - Turn off triad display.
- `LBOT` - Display triad in lower left screen corner.
- `RBOT` - Display triad in lower right screen corner.
- `LTOP` - Display triad in upper left screen corner.
- `RTOP` - Display triad in upper right screen corner.

## Notes

For efficiency, Mechanical APDL maintains a single data structure (segment) which includes the triad as a 3D data object.

If a 3D device is involved ( [[show|/SHOW]],3D) and the graphics are not being displayed as multi- plots, the triad location is determined by the view settings for window \#1.

A request for triad display anywhere except for the origin may yield an improper display in windows 2 through 5.

The program displays the same segment in all windows. The view settings of each window constitute the only difference in the display in the active windows.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TRIAD.html
