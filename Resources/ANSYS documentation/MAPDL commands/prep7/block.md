---
apdl: "BLOCK"
method: block
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.block
generated: 2026-08-22
tags: [mapdl-command]
---

# BLOCK

PyMAPDL: `mapdl.block(x1='', x2='', y1='', y2='', z1='', z2='', **kwargs)`

Creates a block volume based on working plane coordinates.

## Parameters

**x1**, **x2**: Working plane X coordinates of the block.

**y1**, **y2**: Working plane Y coordinates of the block.

**z1**, **z2**: Working plane Z coordinates of the block.

## Returns

`int`: Volume number of the block.

## Notes

Defines a hexahedral volume based on the working plane. The block must have a spatial volume greater than zero (that is, this volume primitive command cannot be used to create a degenerate volume as a means of creating an area.) The volume will be defined with eight keypoints, twelve lines, and six areas, with the top and bottom faces parallel to the working plane. See the [[blc4|BLC4]] and [[blc5|BLC5]] commands for alternate ways to create blocks.

## Examples

Create a block volume based on working plane coordinates with the size `(1 x 2 x 3)`.

``` python
>>> vnum = mapdl.block(0, 1, 0, 2, 1, 4)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BLOCK.html
