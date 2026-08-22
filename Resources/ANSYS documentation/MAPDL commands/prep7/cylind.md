---
apdl: "CYLIND"
method: cylind
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.cylind
generated: 2026-08-22
tags: [mapdl-command]
---

# CYLIND

PyMAPDL: `mapdl.cylind(rad1='', rad2='', z1='', z2='', theta1='', theta2='', **kwargs)`

Creates a cylindrical volume centered about the working plane origin.

## Parameters

**rad1**, **rad2**: Inner and outer radii (either order) of the cylinder. A value of zero or blank for either `RAD1` or `RAD2`, or the same value for both `RAD1` and `RAD2`, defines a solid cylinder.

**z1**, **z2**: Working plane Z coordinates of the cylinder. If either `Z1` or `Z2` is zero, one of the faces of the cylinder will be coplanar with the working plane.

**theta1**, **theta2**: Starting and ending angles (either order) of the cylinder. Used for creating a cylindrical sector. The sector begins at the algebraically smaller angle, extends in a positive angular direction, and ends at the larger angle. The starting angle defaults to 0.0° and the ending angle defaults to 360.0°. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration.

## Returns

`int`: Volume number of the cylinder.

## Notes

Defines a cylindrical volume centered about the working plane origin. The top and bottom faces are parallel to the working plane but neither face need be coplanar with (that is, "on") the working plane. The cylinder must have a spatial volume greater than zero. (that is, this volume primitive command cannot be used to create a degenerate volume as a means of creating an area.) For a solid cylinder of 360°, the top and bottom faces will be circular (each area defined with four lines), and they will be connected with two areas (each spanning 180°.) See the [[cyl4|CYL4]] and [[cyl5|CYL5]] commands for alternate ways to create cylinders.

## Examples

Create a hollow cylinder with an inner radius of 0.9 and an outer radius of 1.0 with a height of 5

``` python
>>> vnum = mapdl.cylind(0.9, 1, z1=0, z2=5)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYLIND.html
