---
apdl: "LFILLT"
method: lfillt
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lfillt
generated: 2026-08-22
tags: [mapdl-command]
---

# LFILLT

PyMAPDL: `mapdl.lfillt(nl1='', nl2='', rad='', pcent='', **kwargs)`

Generates a fillet line between two intersecting lines.

## Parameters

**nl1**: Number of the first intersecting line. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**nl2**: Number of the second intersecting line.

**rad**: Radius of fillet to be generated. Radius should be less than the lengths of the two lines specified with `NL1` and `NL2`.

**pcent**: Number to be assigned to generated keypoint at fillet arc center. If zero (or blank), no keypoint is generated.

## Returns

`int`: Line number of the generated line.

## Notes

Generates a fillet line between two intersecting lines `NL1` ( `P1` - `PINT` ) and `NL2` ( `P2` - `PINT` ). Three keypoints may be generated, two at the fillet tangent points ( `PTAN1` and `PTAN2` ) and one (optional) at the fillet arc center ( `PCENT` ). Line `P1` - `PINT` becomes `P1` - `PTAN1`, `P2` - `PINT` becomes `P2` - `PTAN2`, and new arc line `PTAN1` - `PTAN2` is generated. Generated keypoint and line numbers are automatically assigned (beginning with the lowest available values ( [[numstr|NUMSTR]] )). Line divisions are set to zero (use [[lesize|LESIZE]], etc. to modify).

## Examples

Create two intersecting lines at a right angle and add a fillet between them.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 0, 1, 0)
>>> k2 = mapdl.k("", 1, 0, 0)
>>> l0 = mapdl.l(k0, k1)
>>> l1 = mapdl.l(k0, k2)
>>> lnum = mapdl.lfillt(l0, l1, 0.25)
3
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LFILLT.html
