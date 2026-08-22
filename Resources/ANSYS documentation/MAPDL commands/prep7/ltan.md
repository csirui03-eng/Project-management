---
apdl: "LTAN"
method: ltan
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.ltan
generated: 2026-08-22
tags: [mapdl-command]
---

# LTAN

PyMAPDL: `mapdl.ltan(nl1='', p3='', xv3='', yv3='', zv3='', **kwargs)`

Generates a line at the end of, and tangent to, an existing line.

## Parameters

**nl1**: Number of the line the generated line is tangent to. If negative, assume `P1` (see below), instead of `P2`, is the second keypoint of line `NL1`. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**p3**: Keypoint at which generated line must end.

**xv3**, **yv3**, **zv3**: Location (in the active coordinate system) of the head of the "slope vector" corresponding to the slope at the `P3` end of the line. The tail of the vector is at the coordinate system origin.

## Returns

`int`: Line number of the line generated.

## Notes

Generates a line ( `P2` - `P3` ) tangent at end point ( `P2` ) of line `NL1` ( `P1` - `P2` ).

## Examples

Create a circular arc and generate a tangent spline at the end of it directed to a new keypoint.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 0, 0, 1)
>>> k2 = mapdl.k("", -1, 1.5, 0)
>>> carc = mapdl.circle(k0, 1, k1, arc=90)
>>> lnum = mapdl.ltan(carc[0], k2)
>>> lnum
2
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LTAN.html
