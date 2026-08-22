---
apdl: "KMOVE"
method: kmove
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kmove
generated: 2026-08-22
tags: [mapdl-command]
---

# KMOVE

PyMAPDL: `mapdl.kmove(npt='', kc1='', x1='', y1='', z1='', kc2='', x2='', y2='', z2='', **kwargs)`

Calculates and moves a keypoint to an intersection.

## Parameters

**npt**: Move this keypoint. If `NPT` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NPT`.

**kc1**: First coordinate system number. Defaults to 0 (global Cartesian).

**x1**, **y1**, **z1**: Input one or two values defining the location of the keypoint in this coordinate system. Input "U" for unknown value(s) to be calculated and input "E" to use an existing coordinate value. Fields are R1, θ1, Z1 for cylindrical, or R1, θ1, ϕ1 for spherical.

**kc2**: Second coordinate system number.

**x2**, **y2**, **z2**: Input two or one value(s) defining the location of the keypoint in this coordinate system. Input U for unknown value(s) to be calculated and input E to use an existing coordinate value. Arguments are R2, θ2, Z2 for cylindrical, or R2, θ2, ϕ2 for spherical.

## Notes

Calculates and moves a keypoint to an intersection location. The keypoint must have been previously defined (at an approximate location) or left undefined (in which case it is internally defined at the [[source|SOURCE]] location). The actual location is calculated from the intersection of three surfaces (implied from three coordinate constants in two different coordinate systems). Note that solid modeling in a toroidal coordinate system is not recommended. See the [[move|MOVE]] command for surface and intersection details. The three (of six) constants easiest to define should be used. The program will calculate the remaining three coordinate constants. All arguments, except `KC1`, must be input. Use the repeat command ( `*REPEAT` ) after the **KMOVE** command to move a series of keypoints, if desired.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KMOVE.html
