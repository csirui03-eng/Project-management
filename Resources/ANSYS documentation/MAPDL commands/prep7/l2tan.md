---
apdl: "L2TAN"
method: l2tan
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.l2tan
generated: 2026-08-22
tags: [mapdl-command]
---

# L2TAN

PyMAPDL: `mapdl.l2tan(nl1='', nl2='', **kwargs)`

Generates a line tangent to two lines.

## Parameters

**nl1**: Number of the first line generated line is tangent to. If negative, assume `P1` (see below) is the second keypoint of the line instead of the first. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**nl2**: Number of the second line generated line is tangent to. If negative, assume `P3` is the second keypoint of the line instead of the first.

## Returns

`int`: Line number of the generated line.

## Notes

Generates a line ( `P2` - `P3` ) tangent at point `P2` to line `NL1` ( `P1` - `P2` ) and tangent at point `P3` to line `NL2` ( `P3` - `P4` ).

## Examples

Create two circular arcs and connect them with a spline.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 0, 0, 1)
>>> k2 = mapdl.k("", -1.5, 1.5, 0)
>>> k3 = mapdl.k("", -1.5, 1.5, 1)
>>> carc0 = mapdl.circle(k0, 1, k1, arc=90)
>>> carc1 = mapdl.circle(k2, 1, k3, arc=90)
>>> lnum = mapdl.l2tan(1, 2)
3
```

Plot these lines

``` python
>>> mapdl.lplot(cpos='xy')
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_L2TAN.html
