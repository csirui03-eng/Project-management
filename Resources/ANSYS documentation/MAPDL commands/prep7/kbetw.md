---
apdl: "KBETW"
method: kbetw
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kbetw
generated: 2026-08-22
tags: [mapdl-command]
---

# KBETW

PyMAPDL: `mapdl.kbetw(kp1='', kp2='', kpnew='', type_='', value='', **kwargs)`

Creates a keypoint between two existing keypoints.

## Parameters

**kp1**: First keypoint. If `KP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**kp2**: Second keypoint.

**kpnew**: Number assigned to the new keypoint. Defaults to the lowest available keypoint number.

**type_**

Type of input for `VALUE`.

- `RATIO` - Value is the ratio of the distances between keypoints as follows: ( `KP1` - `KPNEW` )/( `KP1` - `KP2` ).
- `DIST` - Value is the absolute distance between `KP1` and `KPNEW` (valid only if current coordinate system is Cartesian).

**value**: Location of new keypoint, as defined by `Type` (defaults to 0.5). If `VALUE` is a ratio ( `Type` = RATIO) and is less than 0 or greater than 1, the keypoint is created on the extended line. Similarly, if `VALUE` is a distance ( `Type` = DIST) and is less than 0 or greater than the distance between `KP1` and `KP2`, the keypoint is created on the extended line.

## Returns

`int`: Keypoint number of the generated keypoint.

## Notes

Placement of the new keypoint depends on the currently active coordinate system ( [[csys|CSYS]] ). If the coordinate system is Cartesian, the keypoint will lie on a straight line between `KP1` and `KP2`. If the system is not Cartesian (for example, cylindrical, spherical, etc.), the keypoint will be located as if on a line (which may not be straight) created in the current coordinate system between `KP1` and `KP2`. Note that solid modeling in a toroidal coordinate system is not recommended.

## Examples

Create a keypoint exactly centered between two keypoints.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.kbetw(k0, k1)
>>> k2
3
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KBETW.html
