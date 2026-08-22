---
apdl: "RECTNG"
method: rectng
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.rectng
generated: 2026-08-22
tags: [mapdl-command]
---

# RECTNG

PyMAPDL: `mapdl.rectng(x1='', x2='', y1='', y2='', **kwargs)`

Creates a rectangular area anywhere on the working plane.

## Parameters

**x1**, **x2**: Working plane X coordinates of the rectangle.

**y1**, **y2**: Working plane Y coordinates of the rectangle.

## Notes

The area will be defined with four keypoints and four lines. See the [[blc4|BLC4]] and [[blc5|BLC5]] commands for alternate ways to create rectangles.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_RECTNG.html
