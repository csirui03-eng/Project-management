---
apdl: "/NORMAL"
method: normal
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.style.Style.normal
generated: 2026-08-22
tags: [mapdl-command]
---

# /NORMAL

PyMAPDL: `mapdl.normal(wn='', key='', **kwargs)`

Allows displaying area elements by top or bottom faces.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**key**

Display key:

- `0` - No face distinction.
- `1` - Show only area elements having their positive normals directed toward the viewing point.
- `-1` - Show only area elements having their positive normals directed away from the viewing point.

## Notes

**/NORMAL** allows you to select area elements and area plots by the top or bottom faces. It is useful for checking the normal directions on shell elements. The positive normal (element Z direction) is defined by the right-hand rule following the node I, J, K, L input direction. This command is available only with raster or hidden-line displays, for WIN32 or X11 2D displays only.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_NORMAL.html
