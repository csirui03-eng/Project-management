---
apdl: "LARC"
method: larc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.larc
generated: 2026-08-22
tags: [mapdl-command]
---

# LARC

PyMAPDL: `mapdl.larc(p1='', p2='', pc='', rad='', **kwargs)`

Defines a circular arc.

## Parameters

**p1**: Keypoint at one end of circular arc line. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**p2**: Keypoint at other end of circular arc line.

**pc**: Keypoint defining plane of arc and center of curvature side (with positive radius). Must not lie along the straight line from `P1` to `P2`. `PC` need not be at the center of curvature.

**rad**: Radius of curvature of the arc. If negative, assume center of curvature side is opposite to that defined by `PC`. If `RAD` is blank, `RAD` will be calculated from a curve fit through `P1`, `PC`, and `P2`.

## Returns

`int`: Line number of the arc.

## Notes

Defines a circular arc line from `P1` to `P2`. The line shape is generated as circular, regardless of the active coordinate system. The line shape is invariant with coordinate system after it is generated.

When dealing with a large radius arc (1e3), or if the location of the arc you create is far away from the origin of your coordinate system, anomalies may occur. You can prevent this by creating the arc at a smaller scale, and then scaling the model back to full size ( [[lsscale|LSSCALE]] ).

## Examples

Create a circular arc that travels between (0, 0, 0) and (1, 1, 0) with a radius of curvature of 2.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 1, 0)
>>> k2 = mapdl.k("", 0, 1, 0)
>>> lnum = mapdl.larc(k0, k1, k2, 2)
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LARC.html
