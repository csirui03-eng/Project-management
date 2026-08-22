---
apdl: "BLC4"
method: blc4
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.blc4
generated: 2026-08-22
tags: [mapdl-command]
---

# BLC4

PyMAPDL: `mapdl.blc4(xcorner='', ycorner='', width='', height='', depth='', **kwargs)`

Creates a rectangular area or block volume by corner points.

## Parameters

**xcorner**, **ycorner**: Working plane X and Y coordinates of one corner of the rectangle or block face.

**width**: The distance from `XCORNER` on or parallel to the working plane X-axis that, together with `YCORNER`, defines a second corner of the rectangle or block face.

**height**: The distance from `YCORNER` on or parallel to the working plane Y-axis that, together with `XCORNER`, defines a third corner of the rectangle or block face.

**depth**: The perpendicular distance (either positive or negative based on the working plane Z direction) from the working plane representing the depth of the block. If `DEPTH` = 0 (default), a rectangular area is created on the working plane.

## Returns

`int`: Volume or area number of the block or rectangle.

## Notes

Defines a rectangular area anywhere on the working plane or a hexahedral volume with one face anywhere on the working plane. A rectangle will be defined with four keypoints and four lines. A volume will be defined with eight keypoints, twelve lines, and six areas, with the top and bottom faces parallel to the working plane. See the [[blc5|BLC5]], [[rectng|RECTNG]], and [[block|BLOCK]] commands for alternate ways to create rectangles and blocks.

## Examples

Create a block with dimensions 1 x 2 x 10 with one corner of the block at (0, 0) of the current working plane.

``` python
>>> vnum = mapdl.blc4(1, 1, 1, 2, 10)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BLC4.html
