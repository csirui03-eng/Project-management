---
apdl: "/CLABEL"
method: clabel
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.clabel
generated: 2026-08-22
tags: [mapdl-command]
---

# /CLABEL

PyMAPDL: `mapdl.clabel(wn='', key='', **kwargs)`

Specifies contour labeling.

**Command default:**

Show contour line labels.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**key**

Labeling key:

- `0 or 1` - Label contours with legend or color (default).
- `-1` - No contour labeling.
- `N` - Same as 1 except show alphabetic legend only on every `N` th element.

## Notes

Labels contours for identification with alphabetic legend for vector displays and color for raster displays. Number of contours is automatically reduced to 9 (or fewer) for clarity. Use [[contour|/CONTOUR]] command to increase (24 maximum for alphabetic labeling; no limit for color labeling).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CLABEL.html
