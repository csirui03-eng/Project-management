---
apdl: "SPH4"
method: sph4
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.sph4
generated: 2026-08-22
tags: [mapdl-command]
---

# SPH4

PyMAPDL: `mapdl.sph4(xcenter='', ycenter='', rad1='', rad2='', **kwargs)`

Creates a spherical volume anywhere on the working plane.

## Parameters

**xcenter**, **ycenter**: Working plane X and Y coordinates of the center of the sphere.

**rad1**, **rad2**: Inner and outer radii (either order) of the sphere. A value of zero or blank for either `RAD1` or `RAD2` defines a solid sphere.

## Returns

`int`: Volume number of the sphere.

## Notes

Defines either a solid or hollow spherical volume anywhere on the working plane. The sphere must have a spatial volume greater than zero. (that is, this volume primitive command cannot be used to create a degenerate volume as a means of creating an area.) A sphere of 360° will be defined with two areas, each consisting of a hemisphere. See the [[sphere|SPHERE]] and [[sph5|SPH5]] commands for other ways to create spheres.

When working with a model imported from an IGES file (DEFAULT import option), you can create only solid spheres. If you enter a value for both `RAD1` and `RAD2` the command is ignored.

## Examples

This example creates a hollow sphere with an inner radius of 0.9 and an outer radius of 1.0 centered at `(0, 0)`

``` python
>>> vnum = mapdl.sph4(0, 0, rad1=0.9, rad2=1.0)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPH4.html
