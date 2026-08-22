---
apdl: "LSTR"
method: lstr
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.lines.Lines.lstr
generated: 2026-08-22
tags: [mapdl-command]
---

# LSTR

PyMAPDL: `mapdl.lstr(p1='', p2='', **kwargs)`

Defines a straight line irrespective of the active coordinate system.

## Parameters

**p1**: Keypoint at the beginning of line. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI)

**p2**: Keypoint at the end of line.

## Returns

`int`: Line number of the generated line.

## Notes

Defines a straight line from `P1` to `P2` using the global Cartesian coordinate system. The active coordinate system will be ignored. The line shape is invariant with the coordinate system after it is generated. Lines may be redefined only if not yet attached to an area.

## Examples

Create a cartesian straight line regardless of the coordinate system being in cylindrical.

``` python
>>> mapdl.csys(1)
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 1, 1)
>>> lnum = mapdl.lstr(k0, k1)
>>> lnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LSTR.html
