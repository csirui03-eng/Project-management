---
apdl: "CYL5"
method: cyl5
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.cyl5
generated: 2026-08-22
tags: [mapdl-command]
---

# CYL5

PyMAPDL: `mapdl.cyl5(xedge1='', yedge1='', xedge2='', yedge2='', depth='', **kwargs)`

Creates a circular area or cylindrical volume by end points.

## Parameters

**xedge1**, **yedge1**: Working plane X and Y coordinates of one end of the circle or cylinder face.

**xedge2**, **yedge2**: Working plane X and Y coordinates of the other end of the circle or cylinder face.

**depth**: The perpendicular distance (either positive or negative based on the working plane Z direction) from the working plane representing the depth of the cylinder. If `DEPTH` = 0 (default), a circular area is created on the working plane.

## Returns

`int`: Volume or area number of the circular area of cylindrical volume.

## Notes

Defines a circular area anywhere on the working plane or a cylindrical volume with one face anywhere on the working plane by specifying diameter end points. For a solid cylinder of 360°, the top and bottom faces will be circular (each area defined with four lines) and they will be connected with two surface areas (each spanning 180°). See the [[cyl4|CYL4]], [[pcirc|PCIRC]], and [[cylind|CYLIND]] commands for alternate ways to create circles and cylinders.

## Examples

Create a circular with one point of the circle at `(1, 1)` and the other point at `(2, 2)`

``` python
>>> anum = mapdl.cyl5(xedge1=1, yedge1=1, xedge2=2, yedge2=2)
>>> anum
1
```

Create a cylinder with one point of the circle at `(X, Y) == (1, 1)` and the other point at `(X, Y) == (2, 2)` with a height of 3.

``` python
>>> vnum = mapdl.cyl5(xedge1=1, yedge1=1, xedge2=2, yedge2=2, depth=5)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYL5.html
