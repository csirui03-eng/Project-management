---
apdl: "/NUMBER"
method: number
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.labeling.Labeling.number
generated: 2026-08-22
tags: [mapdl-command]
---

# /NUMBER

PyMAPDL: `mapdl.number(nkey='', **kwargs)`

Specifies whether numbers, colors, or both are used for displays.

## Parameters

**nkey**

Numbering style:

- `0` - Color (terminal dependent) the numbered items and show numbers.
- `1` - Color the numbered items. Do not show the numbers.
- `2` - Show the numbers. Do not color the items.
- `-1` - Do not color the items or show the numbers. For contour plots, the resulting display will vary (see below).

## Notes

Specifies whether numbers, colors, or both are used for numbering displays ( [[pnum|/PNUM]] ) of nodes, elements, keypoints, lines, areas, and volumes.

Shading is also available for terminals configured with more than 4 color planes ( [[show|/SHOW]] ). Color automatically appears for certain items and may be manually controlled (off or on) for other items.

When you suppress color ( `NKEY` = -1) your contour plots will produce different results, depending on your graphics equipment. For non-3D devices (X11, Win32, etc.) your contour plot will be white (no color). For 3D devices, such as OpenGL, the resulting display will be in color.

The following items are automatically given discrete colors: Boundary condition symbols ( [[pbc|/PBC]] ), curves on graph displays, and distorted geometry on postprocessing displays. Contour lines in postprocessing displays are automatically colored based upon a continuous, rather than a discrete, spectrum so that red is associated with the highest contour value. On terminals with raster capability ( [[show|/SHOW]] ), the area between contour lines is filled with the color of the higher contour.

Explicit entity colors or the discrete color mapping may be changed with the [[color|/COLOR]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NUMBER.html
