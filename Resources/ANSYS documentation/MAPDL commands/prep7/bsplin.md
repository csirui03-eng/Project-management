---
apdl: "BSPLIN"
method: bsplin
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.bsplin
generated: 2026-08-22
tags: [mapdl-command]
---

# BSPLIN

PyMAPDL: `mapdl.bsplin(p1='', p2='', p3='', p4='', p5='', p6='', xv1='', yv1='', zv1='', xv6='', yv6='', zv6='', **kwargs)`

Generates a single line from a spline fit to a series of keypoints.

## Parameters

**p1**, **p2**, **p3**, **p4**, **p5**, **p6**

Keypoints through which a spline is fit. At least two keypoints must be defined. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

The following fields are used only if specified end slopes are desired; otherwise, zero curvature end slopes will be automatically calculated. The slope vector is parallel to a vector pointing from the origin of the active coordinate system ( [[csys|CSYS]] ) to the position in space that XV, YV, ZV represents in that system.

**xv1**, **yv1**, **zv1**: Orientation point of an outward vector tangent to line at `P1`. Vector coordinate system has its origin at the keypoint. Coordinate interpretation corresponds to the active coordinate system type, that is, X is R for cylindrical, etc. Defaults to zero curvature slope.

**xv6**, **yv6**, **zv6**: Orientation point of an outward vector tangent to a line at `P6` (or the last keypoint specified if fewer than six specified). Defaults to zero curvature slope.

## Returns

`int`: Line number of the spline generated from the spline fit.

## Notes

One line is generated between keypoint `P1` and the last keypoint entered. The line will pass through each entered keypoint. Solid modeling in a toroidal coordinate system is not recommended.

## Examples

Generate a spline through `(0, 0, 0)`, `(0, 1, 0)` and `(1, 2, 0)`

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 0, 1, 0)
>>> k2 = mapdl.k("", 1, 2, 0)
>>> lnum = mapdl.bsplin(k0, k1, k2)
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_BSPLIN.html
