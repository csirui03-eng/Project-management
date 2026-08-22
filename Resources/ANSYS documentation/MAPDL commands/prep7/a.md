---
apdl: "A"
method: a
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.a
generated: 2026-08-22
tags: [mapdl-command]
---

# A

PyMAPDL: `mapdl.a(p1='', p2='', p3='', p4='', p5='', p6='', p7='', p8='', p9='', p10='', p11='', p12='', p13='', p14='', p15='', p16='', p17='', p18='', **kwargs)`

Defines an area by connecting keypoints.

## Parameters

**p1**, **p2**, **p3**, **p4**, **p5**, **p6**, **p7**, **p8**, **p9**, **p10**, **p11**, **p12**, **p13**, **p14**, **p15**, **p16**, **p17**, **p18**: List of keypoints defining the area (18 maximum if using keyboard entry). At least 3 keypoints must be entered. If `P1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI).

## Returns

`int`: The area number of the generated area.

## Notes

Keypoints ( `P1` through `P18` ) must be input in a clockwise or counterclockwise order around the area. This order also determines the positive normal direction of the area according to the right-hand rule. Existing lines between adjacent keypoints will be used; missing lines are generated "straight" in the active coordinate system and assigned the lowest available numbers ( [[numstr|NUMSTR]] ). If more than one line exists between two keypoints, the shorter one will be chosen. If the area is to be defined with more than four keypoints, the required keypoints and lines must lie on a constant coordinate value in the active coordinate system (such as a plane or a cylinder). Areas may be redefined only if not yet attached to a volume. Solid modeling in a toroidal coordinate system is not recommended.

## Examples

Create a simple triangle in the XY plane using three keypoints.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.k("", 0, 1, 0)
>>> a0 = mapdl.a(k0, k1, k2)
>>> a0
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_A.html
