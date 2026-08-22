---
apdl: "SPHERE"
method: sphere
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.sphere
generated: 2026-08-22
tags: [mapdl-command]
---

# SPHERE

PyMAPDL: `mapdl.sphere(rad1='', rad2='', theta1='', theta2='', **kwargs)`

Creates a spherical volume centered about the working plane origin.

## Parameters

**rad1**, **rad2**: Inner and outer radii (either order) of the sphere. A value of zero or blank for either `RAD1` or `RAD2` defines a solid sphere.

**theta1**, **theta2**: Starting and ending angles (either order) of the sphere. Used for creating a spherical sector. The sector begins at the algebraically smaller angle, extends in a positive angular direction, and ends at the larger angle. The starting angle defaults to 0.0° and the ending angle defaults to 360.0°. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration.

## Returns

`int`: Volume number of the sphere.

## Notes

Defines either a solid or hollow sphere or spherical sector centered about the working plane origin. The sphere must have a spatial volume greater than zero. (that is, this volume primitive command cannot be used to create a degenerate volume as a means of creating an area.) Inaccuracies can develop when the size of the object you create is much smaller than the relative coordinate system values (ratios near to or greater than 1000). If you require an exceptionally small sphere, create a larger object, and scale it down to the appropriate size.

For a solid sphere of 360°, you define it with two areas, each consisting of a hemisphere. See the [[sph4|SPH4]] and [[sph5|SPH5]] commands for the other ways to create spheres.

## Examples

``` python
>>> vnum = mapdl.sphere(rad1=0.95, rad2=1.0, theta1=90, theta2=270)
>>> vnum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SPHERE.html
