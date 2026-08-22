---
apdl: "SPH5"
method: sph5
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.sph5
generated: 2026-08-22
tags: [mapdl-command]
---

# SPH5

PyMAPDL: `mapdl.sph5(xedge1='', yedge1='', xedge2='', yedge2='', **kwargs)`

Creates a spherical volume by diameter end points.

## Parameters

**xedge1**, **yedge1**: Working plane X and Y coordinates of one edge of the sphere.

**xedge2**, **yedge2**: Working plane X and Y coordinates of the other edge of the sphere.

## Returns

`int`: Volume number of the sphere.

## Notes

Defines a solid spherical volume anywhere on the working plane by specifying diameter end points. The sphere must have a spatial volume greater than zero. (that is, this volume primitive command cannot be used to create a degenerate volume as a means of creating an area.) A sphere of 360° will be defined with two areas, each consisting of a hemisphere. See the [[sphere|SPHERE]] and [[sph4|SPH4]] commands for other ways to create spheres.

## Examples

This example creates a sphere with one point at `(1, 1)` and one point at `(2, 2)`

``` python
>>> vnum = mapdl.sph5(xedge1=1, yedge1=1, xedge2=2, yedge2=2)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPH5.html
