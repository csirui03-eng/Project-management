---
apdl: "SPLINE"
method: spline
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.spline
generated: 2026-08-22
tags: [mapdl-command]
---

# SPLINE

PyMAPDL: `mapdl.spline(p1='', p2='', p3='', p4='', p5='', p6='', xv1='', yv1='', zv1='', xv6='', yv6='', zv6='', **kwargs)`

Generates a segmented spline through a series of keypoints.

## Parameters

**p1**, **p2**, **p3**, **p4**, **p5**, **p6**: Keypoints through which the spline is fit. At least two must be defined. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**xv1**, **yv1**, **zv1**: Location (in the active coordinate system) of the head of the "slope vector" corresponding to the slope at the `P1` end of the spline. The tail of the vector is at the origin of the coordinate system.

**xv6**, **yv6**, **zv6**: Location of the head of the "slope vector" corresponding to the slope at the `P6` (or the last keypoint if fewer than six specified) end of the spline.

## Returns

`list`: List of line numbers generated.

## Notes

The output from this command is a series of connected lines (one line between each pair of keypoints) that together form a spline. Note that solid modeling in a toroidal coordinate system is not recommended.

## Examples

Create a spline with 5 keypoints.

``` python
>>> k0 = mapdl.k('', 0, 0, 0)
>>> k1 = mapdl.k('', 0.2, 0.2, 0)
>>> k2 = mapdl.k('', 0.4, 0.3, 0)
>>> k3 = mapdl.k('', 0.6, 0.5, 0)
>>> k4 = mapdl.k('', 0.8, 0.3, 0)
>>> lines = mapdl.spline(k0, k1, k2, k3, k4)
>>> lines
[1, 2, 3, 4]
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPLINE.html
