---
apdl: "AL"
method: al
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.al
generated: 2026-08-22
tags: [mapdl-command]
---

# AL

PyMAPDL: `mapdl.al(l1='', l2='', l3='', l4='', l5='', l6='', l7='', l8='', l9='', l10='', **kwargs)`

Generates an area bounded by previously defined lines.

## Parameters

**l1**, **l2**, **l3**, **l4**, **l5**, **l6**, **l7**, **l8**, **l9**, **l10**: List of lines defining area. The minimum number of lines is 3. The positive normal of the area is controlled by the direction of `L1` using the right-hand rule. A negative value of `L1` reverses the normal direction. If `L1` = ALL, use all selected lines with `L2` defining the normal ( `L3` to `L10` are ignored and `L2` defaults to the lowest numbered selected line). If `L1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `L1`.

## Returns

`int`: Area number of the generated area.

## Notes

Lines may be input (once each) in any order and must form a simply connected closed curve. If the area is defined with more than four lines, the lines must also lie in the same plane or on a constant coordinate value in the active coordinate system (such as a plane or a cylinder). Solid modeling in a toroidal coordinate system is not recommended. Areas may be redefined only if not yet attached to a volume.

This command is valid in any processor.

## Examples

Create an area from four lines

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.k("", 1, 1, 0)
>>> k3 = mapdl.k("", 0, 1, 0)
>>> l0 = mapdl.l(k0, k1)
>>> l1 = mapdl.l(k1, k2)
>>> l2 = mapdl.l(k2, k3)
>>> l3 = mapdl.l(k3, k0)
>>> anum = mapdl.al(l0, l1, l2, l3)
>>> anum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AL.html
