---
apdl: "LANG"
method: lang
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lang
generated: 2026-08-22
tags: [mapdl-command]
---

# LANG

PyMAPDL: `mapdl.lang(nl1='', p3='', ang='', phit='', locat='', **kwargs)`

Generates a straight line at an angle with a line.

## Parameters

**nl1**: Number of the line to be hit (touched by the end of the new line). If negative, assume `P1` (see below) is the second keypoint of the line instead of the first. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**p3**: Keypoint at which generated line must end.

**ang**: Angle of intersection of generated line `PHIT` - `P3` with tangent to line `P1` - `P2` at `PHIT`. If 0 (default), the generated line is tangent to `NL1` toward end P1; if 90, the generated line is perpendicular to `NL1`. If 180, the generated line is tangent to NL1 toward end P2. `ANG` can be any value, but is adjusted to the corresponding acute angle with respect to `LOCAT`. See [[lang#Notes|LANG]] for a discussion of accuracy.

**phit**: Number to be assigned to keypoint generated at hit location (defaults to lowest available keypoint number ( [[numstr|NUMSTR]] )).

**locat**: Approximate location of `PHIT` in terms of the ratio of the distance along the line ( `NL1` ) to the length of the line. `LOCAT` can range from 0 to 1. If `LOCAT` is blank, the point will be located with less speed and accuracy, and an arbitrary location may result.

## Returns

`int`: Line number of the generated line.

## Notes

Generates a straight line ( `PHIT` - `P3` ) at an angle ( `ANG` ) with a line `NL1` ( `P1` - `P2` ). The location of `PHIT` on the line is automatically calculated. Line `P1` - `P2` becomes `P1` - `PHIT` and new lines `PHIT` - `P2` and `PHIT` - `P3` are generated. Line divisions are set to zero (use [[lesize|LESIZE]], etc. to modify).

`PHIT` is positioned closest to `LOCAT` for the given angle, `ANG`. To ensure better performance, it is recommended that `LOCAT` be input, even if it is 0.

The program uses an iterative procedure to position `PHIT`. The procedure is not exact, with the result that the actual value of `ANG` will sometimes differ slightly from the specified value.

## Examples

Create a line from a line from (0, 0, 0) to (1, 0, 0) to a keypoint at (1, 1, 1) at an angle of 60 degrees.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> lnum = mapdl.l(k0, k1)
>>> k2 = mapdl.k("", 1, 1, 0)
>>> lnum = mapdl.lang(lnum, k2, 60)
>>> lnum
2
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LANG.html
