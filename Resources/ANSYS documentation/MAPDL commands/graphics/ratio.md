---
apdl: "/RATIO"
method: ratio
group: graphics
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.graphics.scaling.Scaling.ratio
generated: 2026-08-22
tags: [mapdl-command]
---

# /RATIO

PyMAPDL: `mapdl.ratio(wn='', ratox='', ratoy='', **kwargs)`

Distorts the object geometry.

## Parameters

**wn**: Window number (or ALL) to which command applies (defaults to 1).

**ratox**: Distort object in the window X direction by this factor (defaults to 1.0).

**ratoy**: Distort object in the window Y direction by this factor (defaults to 1.0).

## Notes

Distorts the object geometry in a particular direction. An example of this command's use would be to allow long narrow sections to be distorted to a more square area for better display visualization.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RATIO.html
