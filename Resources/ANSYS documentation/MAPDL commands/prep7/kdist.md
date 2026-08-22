---
apdl: "KDIST"
method: kdist
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.kdist
generated: 2026-08-22
tags: [mapdl-command]
---

# KDIST

PyMAPDL: `mapdl.kdist(kp1='', kp2='', **kwargs)`

Calculates and lists the distance between two keypoints.

## Parameters

**kp1**: First keypoint in distance calculation. If `KP1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**kp2**: Second keypoint in distance calculation.

## Returns

`list`: `[DIST, X, Y, Z]` distance between two keypoints.

## Notes

**KDIST** lists the distance between keypoints `KP1` and `KP2`, as well as the current coordinate system offsets from `KP1` to `KP2`, where the X, Y, and Z locations of `KP1` are subtracted from the X, Y, and Z locations of `KP2` (respectively) to determine the offsets. **KDIST** is valid in any coordinate system except toroidal ( [[csys|CSYS]],3).

**KDIST** returns a variable, called `_RETURN`, which contains the distance value. You can use this value for various purposes; for example, to set the default number of line divisions to be generated along region boundary lines ( [[esize|ESIZE]], `_RETURN` ). In interactive mode, you can access this command by using the Model Query Picker ( Utility Menu\> List\> Picked Entities ), where you can also access automatic annotation functions, and display the value on your model.

This command is valid in any processor.

## Examples

Compute the distance between two keypoints.

``` python
>>> kp0 = (0, 10, -3)
>>> kp1 = (1, 5, 10)
>>> knum0 = mapdl.k("", *kp0)
>>> knum1 = mapdl.k("", *kp1)
>>> dist = mapdl.kdist(knum0, knum1)
>>> dist
[13.96424004376894, 1.0, -5.0, 13.0]
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_KDIST.html
