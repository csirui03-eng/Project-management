---
apdl: "LCOMB"
method: lcomb
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lcomb
generated: 2026-08-22
tags: [mapdl-command]
---

# LCOMB

PyMAPDL: `mapdl.lcomb(nl1='', nl2='', keep='', **kwargs)`

Combines adjacent lines into one line.

## Parameters

**nl1**: Number of the first line to be combined. If `NL1` = ALL, `NL2` is ignored and all selected lines ( [[lsel|LSEL]] ) are combined. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` is ignored).

**nl2**: Number of the second line to be combined.

**keep**

Specifies whether to keep the input entities:

- `0` - Delete lines `NL1` and `NL2` and their common keypoint. Keypoints will not be deleted if they are meshed or if they are attached to other lines. Lines will not be deleted if they are attached to different areas.
- `1` - Keep `NL1`, `NL2`, and their common keypoint. (The common keypoint will not be attached to the output line.)

## Returns

`int`: Line number of the combined line.

## Notes

Combines adjacent lines into one line (the output line). This operation will effectively "undo" the [[ldiv|LDIV]] operation. Line divisions are set to zero (use [[lesize|LESIZE]], etc. to modify). Lines attached to the same area(s) can also be combined. See also the [[lccat|LCCAT]] command for line concatenation capability.

## Examples

Create two lines and combine them.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.k("", 2, 0, 0)
>>> l0 = mapdl.l(k0, k1)
>>> l1 = mapdl.l(k0, k2)
>>> lout = mapdl.lcomb(l0, l1)
>>> lout
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCOMB.html
