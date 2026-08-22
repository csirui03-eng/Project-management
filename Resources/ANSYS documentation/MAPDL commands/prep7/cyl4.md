---
apdl: "CYL4"
method: cyl4
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.cyl4
generated: 2026-08-22
tags: [mapdl-command]
---

# CYL4

PyMAPDL: `mapdl.cyl4(xcenter='', ycenter='', rad1='', theta1='', rad2='', theta2='', depth='', **kwargs)`

Creates a circular area or cylindrical volume anywhere on the working plane.

## Parameters

**xcenter**, **ycenter**: Working plane X and Y coordinates of the center of the circle or cylinder.

**rad1**: Inner and outer radii (either order) of the circle or cylinder. A value of zero or blank for either `RAD1` or `RAD2`, or the same value for both `RAD1` and `RAD2`, defines a solid circle or cylinder.

**theta1**: Starting and ending angles (either order) of the circle or faces of the cylinder. Used for creating a partial annulus or partial cylinder. The sector begins at the algebraically smaller angle, extends in a positive angular direction, and ends at the larger angle. The starting angle defaults to 0° and the ending angle defaults to 360°. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration.

**rad2**: Inner and outer radii (either order) of the circle or cylinder. A value of zero or blank for either `RAD1` or `RAD2`, or the same value for both `RAD1` and `RAD2`, defines a solid circle or cylinder.

**theta2**: Starting and ending angles (either order) of the circle or faces of the cylinder. Used for creating a partial annulus or partial cylinder. The sector begins at the algebraically smaller angle, extends in a positive angular direction, and ends at the larger angle. The starting angle defaults to 0° and the ending angle defaults to 360°. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration.

**depth**: The perpendicular distance (either positive or negative based on the working plane Z direction) from the working plane representing the depth of the cylinder. If `DEPTH` = 0 (default), a circular area is created on the working plane.

## Returns

`int`: Volume or area number of the block or rectangle.

## Notes

Defines a circular area anywhere on the working plane or a cylindrical volume with one face anywhere on the working plane. For a solid cylinder of 360°, the top and bottom faces will be circular (each area defined with four lines) and they will be connected with two surface areas (each spanning 180°). See the [[cyl5|CYL5]], [[pcirc|PCIRC]], and [[cylind|CYLIND]] commands for alternate ways to create circles and cylinders.

When working with a model imported from an IGES file (DEFAULT import option), you must provide a value for `DEPTH` or the command will be ignored.

## Examples

Create a half arc centered at the origin with an outer radius of 2 and an inner radius of 1

``` python
>>> anum = mapdl.cyl4(xcenter=0, ycenter=0, rad1=1,
theta1=0, rad2=2, theta2=180)
>>> anum
```

Create a solid cylinder with a depth of 10 at the center of the working plane.

``` python
>>> vnum = mapdl.cyl4(0, 0, 1, depth=10)
>>> vnum
1
```

Create a cylinder with an inner radius of 1.9 and an outer of 2.0 with a height of 5 centered at the working plane.

``` python
>>> vnum = mapdl.cyl4(0, 0, rad1=1.9, rad2=2.0, depth=10)
2
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_CYL4.html
