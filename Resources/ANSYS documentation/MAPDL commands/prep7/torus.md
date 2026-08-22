---
apdl: "TORUS"
method: torus
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.torus
generated: 2026-08-22
tags: [mapdl-command]
---

# TORUS

PyMAPDL: `mapdl.torus(rad1='', rad2='', rad3='', theta1='', theta2='', **kwargs)`

Creates a toroidal volume.

## Parameters

**rad1**, **rad2**, **rad3**: Three values that define the radii of the torus. You can specify the radii in any order. The smallest of the values is the inner minor radius, the intermediate value is the outer minor radius, and the largest value is the major radius. (There is one exception regarding the order of the radii values-if you want to create a solid torus, specify zero or blank for the inner minor radius, in which case the zero or blank must occupy either the `RAD1` or `RAD2` position.) At least two of the values that you specify must be positive values; they will be used to define the outer minor radius and the major radius. See the diagram in the Notes section for a view of a toroidal sector showing all radii.

**theta1**, **theta2**: Starting and ending angles (either order) of the torus. Used for creating a toroidal sector. The sector begins at the algebraically smaller angle, extends in a positive angular direction, and ends at the larger angle. The starting angle defaults to 0° and the ending angle defaults to 360°.

## Returns

`int`: Volume number of the torus.

## Notes

Defines a toroidal volume centered about the working plane origin. A solid torus of 360° will be defined with four areas, each area spanning 180° around the major and minor circumference.

To create the toroidal sector shown below, the command **TORUS**,5,1,2,0,180 was issued. Since "1" was the smallest radii value specified, it defined the inner minor radius; since "2" was the intermediate radii value specified, it defined the outer minor radius; and since "5" was the largest radii value specified, it defined the major radius. The values "0" and "180" defined the starting and ending angles of the torus.

(figure omitted, see the Ansys help page)

## Examples

This example creates a torus with an inner minor radius of 1, an intermediate radii of 2, and a major radius of 5. The values 0 and 180 define the starting and ending angles of the torus.

``` python
>>> vnum = mapdl.torus(rad1=5, rad2=1, rad3=2, theta1=0, theta2=180)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_TORUS.html
