---
apdl: "LAREA"
method: larea
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.larea
generated: 2026-08-22
tags: [mapdl-command]
---

# LAREA

PyMAPDL: `mapdl.larea(p1='', p2='', narea='', **kwargs)`

Generates the shortest line between two keypoints on an area.

## Parameters

**p1**: First keypoint of line to be generated. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**p2**: Second keypoint of line to be generated.

**narea**: Area containing `P1` and `P2`, or area to which generated line is to be parallel.

## Returns

`int`: Line number of the generated line.

## Notes

Generates the shortest line between two keypoints, `P1` and `P2`, both of which lie on an area. The generated line will also lie on the area. `P1` and `P2` may also be equidistant (in global Cartesian space) from the area (and on the same side of the area), in which case a line parallel to the area is generated.

## Examples

Generate a line on a square between its two corners.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.k("", 1, 1, 0)
>>> k3 = mapdl.k("", 0, 1, 0)
>>> a0 = mapdl.a(k0, k1, k2, k3)
>>> lnum = mapdl.larea(k0, k2, a0)
>>> lnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LAREA.html
