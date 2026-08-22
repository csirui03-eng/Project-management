---
apdl: "LEXTND"
method: lextnd
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lextnd
generated: 2026-08-22
tags: [mapdl-command]
---

# LEXTND

PyMAPDL: `mapdl.lextnd(nl1='', nk1='', dist='', keep='', **kwargs)`

Extends a line at one end by using its slope.

## Parameters

**nl1**: Number of the line to be extended. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**nk1**: Number of keypoint at the end of line `NL1` to be extended.

**dist**: Distance that the line will be extended.

**keep**

Specifies whether to keep the input entities:

- `0` - Modify old line to use new keypoints and slopes.
- `1` - Do not modify old line. New line will overlay old line and have unique keypoints.

## Returns

`int`: Line number of the generated line.

## Notes

Extends a line at one end by using its slope. Lines may be redefined only if not yet attached to an area. Line divisions are set to zero (use [[lesize|LESIZE]], etc. to modify). Note that solid modeling in a toroidal coordinate system is not recommended.

## Examples

Create a circular arc and extend it at one of its keypoints

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 0, 0, 1)
>>> carcs = mapdl.circle(k0, 1, k1, arc=90)
>>> lnum = mapdl.lextnd(carcs[0], 3, 1)
>>> lnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LEXTND.html
