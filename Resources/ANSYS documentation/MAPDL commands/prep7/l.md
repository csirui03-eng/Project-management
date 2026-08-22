---
apdl: "L"
method: l
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.l
generated: 2026-08-22
tags: [mapdl-command]
---

# L

PyMAPDL: `mapdl.l(p1='', p2='', ndiv='', space='', xv1='', yv1='', zv1='', xv2='', yv2='', zv2='', **kwargs)`

Defines a line between two keypoints.

## Parameters

**p1**: Keypoint at the beginning of line. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**p2**: Keypoint at the end of line.

**ndiv**: Number of element divisions within this line. Normally this field is not used; specifying divisions with [[lesize|LESIZE]], etc. is recommended.

**space**: Spacing ratio. Normally this field is not used, as specifying spacing ratios with the [[lesize|LESIZE]] command is recommended. If positive, `SPACE` is the nominal ratio of the last division size (at `P2` ) to the first division size (at `P1` ). If the ratio is greater than 1, the division sizes increase from `P1` to `P2`, and if less than 1, they decrease. If `SPACE` is negative, then \| `SPACE` \| is the nominal ratio of the center division size to those at the ends.

**xv1**, **yv1**, **zv1**: Location (in the active coordinate system) of the head of the "slope vector" corresponding to the slope at the `P1` end of the line. The tail of the vector is at the origin of the coordinate system.

**xv2**, **yv2**, **zv2**: Location of the head of the "slope vector" corresponding to the slope at the `P2` end of the line.

## Returns

`int`: The line number of the generated line.

## Notes

Defines a line between two keypoints from `P1` to `P2`. The line shape may be generated as "straight" (in the active coordinate system) or curved. The line shape is invariant with coordinate system after it is generated. Note that solid modeling in a toroidal coordinate system is not recommended. A curved line is limited to 180°. Lines may be redefined only if not yet attached to an area.

## Examples

Create a line between the two keypoints (0, 0, 0) and (1, 0, 0)

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> lnum = mapdl.l(k0, k1)
>>> lnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_L.html
