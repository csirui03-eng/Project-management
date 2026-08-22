---
apdl: "BLC5"
method: blc5
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.blc5
generated: 2026-08-22
tags: [mapdl-command]
---

# BLC5

PyMAPDL: `mapdl.blc5(xcenter='', ycenter='', width='', height='', depth='', **kwargs)`

Creates a rectangular area or block volume by center and corner points.

## Parameters

**xcenter**, **ycenter**: Working plane X and Y coordinates of the center of the rectangle or block face.

**width**: The total distance on or parallel to the working plane X-axis defining the width of the rectangle or block face.

**height**: The total distance on or parallel to the working plane Y-axis defining the height of the rectangle or block face.

**depth**: The perpendicular distance (either positive or negative based on the working plane Z direction) from the working plane representing the depth of the block. If `DEPTH` = 0 (default), a rectangular area is created on the working plane. If you are working with a model imported from an IGES file (import option set to DEFAULT), you must supply a value for `DEPTH` or the command is ignored.

## Returns

`int`: Volume or area number of the block or rectangle.

## Notes

Defines a rectangular area anywhere on the working plane or a hexahedral volume with one face anywhere on the working plane by specifying the center and corner points. A rectangle will be defined with four keypoints and four lines. A volume will be defined with eight keypoints, twelve lines, and six areas, with the top and bottom faces parallel to the working plane. See the [[blc4|BLC4]], [[rectng|RECTNG]], and [[block|BLOCK]] commands for alternate ways to create rectangles and blocks.

## Examples

Create a square centered at `(0, 0)` with a width of 0.5 and a height of 0.5

``` python
>>> anum = mapdl.blc5(width=0.5, height=0.5)
>>> anum
1
```

``` python
>>> vnum = mapdl.blc5(width=1, height=4, depth=9)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BLC5.html
