---
apdl: "KCENTER"
method: kcenter
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kcenter
generated: 2026-08-22
tags: [mapdl-command]
---

# KCENTER

PyMAPDL: `mapdl.kcenter(type_='', val1='', val2='', val3='', val4='', kpnew='', **kwargs)`

Creates a keypoint at the center of a circular arc defined by three locations.

## Parameters

**type_**

Type of entity used to define the circular arc. The meaning of `VAL1` through `VAL4` will vary depending on `Type`. If `Type` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

- `KP` - Arc is defined by keypoints.
- `LINE` - Arc is defined by locations on a line.

**val1**, **val2**, **val3**, **val4**: Values used to specify three locations on the arc (see table below).

**kpnew**: Number assigned to new keypoint. Defaults to the lowest available keypoint number.

## Returns

`int`: Keypoint number of the generated keypoint.

## Notes

**KCENTER** should be used in the Cartesian coordinate system ( [[csys|CSYS]],0) only. This command provides three methods to define a keypoint at the center of three locations. As shown below, the center point can be calculated based on a) three keypoints, b) three keypoints and a radius, or c) three locations on a line. Note that for method c, if a circular line is specified by `VAL1`, `VAL2` through `VAL4` are not needed.

(figure omitted, see the Ansys help page)

## Examples

Create a keypoint at the center of a circle centered at (0, 0, 0)

``` python
>>> k0 = mapdl.k("", 0, 1, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.k("", 0, -1, 0)
>>> k3 = mapdl.kcenter('KP', k0, k1, k2)
>>> k3
4
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KCENTER.html
