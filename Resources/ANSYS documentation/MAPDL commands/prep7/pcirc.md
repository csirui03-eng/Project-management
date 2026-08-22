---
apdl: "PCIRC"
method: pcirc
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.primitives.Primitives.pcirc
generated: 2026-08-22
tags: [mapdl-command]
---

# PCIRC

PyMAPDL: `mapdl.pcirc(rad1='', rad2='', theta1='', theta2='', **kwargs)`

Creates a circular area centered about the working plane origin.

## Parameters

**rad1**, **rad2**: Inner and outer radii (either order) of the circle. A value of either zero or blank for either `RAD1` or `RAD2`, or the same value for both `RAD1` and `RAD2`, defines a solid circle.

**theta1**, **theta2**: Starting and ending angles (either order) of the circular area. Used for creating a circular sector. The sector begins at the algebraically smaller angle, extends in a positive angular direction, and ends at the larger angle. The starting angle defaults to 0.0° and the ending angle defaults to 360.0°. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration.

## Returns

`int`: Area number of the new circular area.

## Notes

Defines a solid circular area or circular sector centered about the working plane origin. For a solid circle of 360°, the area will be defined with four keypoints and four lines. See the [[cyl4|CYL4]] and [[cyl5|CYL5]] commands for alternate ways to create circles.

## Examples

In this example a circular area with an inner radius of 0.95 and an outer radius of 1 is created.

``` python
>>> anum = mapdl.pcirc(0.95, 1)
>>> anum
1
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_PCIRC.html
