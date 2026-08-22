---
apdl: "CONE"
method: cone
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.cone
generated: 2026-08-22
tags: [mapdl-command]
---

# CONE

PyMAPDL: `mapdl.cone(rbot='', rtop='', z1='', z2='', theta1='', theta2='', **kwargs)`

Creates a conical volume centered about the working plane origin.

## Parameters

**rbot**, **rtop**: Radii of the bottom and top faces of the cone. A value of zero or blank for either `RBOT` or `RTOP` defines a degenerate face at the center axis (that is, the vertex of the cone). The same value for both `RBOT` and `RTOP` defines a cylinder instead of a cone.

**z1**, **z2**: Working plane Z coordinates of the cone. The smaller value is always associated with the bottom face.

**theta1**, **theta2**: Starting and ending angles (either order) of the cone. Used for creating a conical sector. The sector begins at the algebraically smaller angle, extends in a positive angular direction, and ends at the larger angle. The starting angle defaults to 0° and the ending angle defaults to 360°. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration.

## Returns

`int`: Volume number of the cone.

## Notes

Defines a solid conical volume centered about the working plane origin. The non-degenerate face (top or bottom) is parallel to the working plane but not necessarily coplanar with (that is, "on") the working plane. The cone must have a spatial volume greater than zero. (that is, this volume primitive command cannot be used to create a degenerate volume as a means of creating an area.) For a cone of 360°, top and bottom faces will be circular (each area defined with four lines), and they will be connected with two areas (each spanning 180°). See the [[con4|CON4]] command for an alternate way to create cones.

## Examples

Create a quarter cone with a bottom radius of 3, top radius of 1 and a height of 10 centered at `(0, 0)`.

``` python
>>> vnum = mapdl.cone(rbot=5, rtop=1, z1=0, z2=10, theta1=180, theta2=90)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CONE.html
