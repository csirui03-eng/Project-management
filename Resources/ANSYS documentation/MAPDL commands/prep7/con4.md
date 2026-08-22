---
apdl: "CON4"
method: con4
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.con4
generated: 2026-08-22
tags: [mapdl-command]
---

# CON4

PyMAPDL: `mapdl.con4(xcenter='', ycenter='', rad1='', rad2='', depth='', **kwargs)`

Creates a conical volume anywhere on the working plane.

## Parameters

**xcenter**, **ycenter**: Working plane X and Y coordinates of the center axis of the cone.

**rad1**, **rad2**: Radii of the faces of the cone. `RAD1` defines the bottom face and will be located on the working plane. `RAD2` defines the top face and is parallel to the working plane. A value of zero or blank for either `RAD1` or `RAD2` defines a degenerate face at the center axis (that is, the vertex of the cone). The same value for both `RAD1` and `RAD2` defines a cylinder instead of a cone.

**depth**: The perpendicular distance (either positive or negative based on the working plane Z direction) from the working plane representing the depth of the cone. `DEPTH` cannot be zero (see [[con4#Notes|CON4]] below).

## Returns

`int`: Volume number of the cone.

## Notes

Defines a solid conical volume with either the vertex or a face anywhere on the working plane. The cone must have a spatial volume greater than zero. (that is, this volume primitive command cannot be used to create a degenerate volume as a means of creating an area.) The face or faces will be circular (each area defined with four lines), and they will be connected with two areas (each spanning 180°). See the [[cone|CONE]] command for an alternate way to create cones.

## Examples

Create a cone with a bottom radius of 3 and a height of 10.

``` python
>>> vnum = mapdl.con4(rad1=3, rad2=0, depth=10)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CON4.html
