---
apdl: "K"
method: k
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.keypoints.Keypoints.k
generated: 2026-08-22
tags: [mapdl-command]
---

# K

PyMAPDL: `mapdl.k(npt='', x='', y='', z='', **kwargs)`

Defines a keypoint.

## Parameters

**npt**: Reference number for keypoint. If zero, the lowest available number is assigned ( [[numstr|NUMSTR]] ).

**x**, **y**, **z**: Keypoint location in the active coordinate system (may be R, θ, Z or R, θ, Φ). If `X` = P, graphical picking is enabled and all other fields (including `NPT` ) are ignored (valid only in the GUI).

## Returns

`int`: The keypoint number of the generated keypoint.

## Notes

Defines a keypoint in the active coordinate system ( [[csys|CSYS]] ) for line, area, and volume descriptions. A previously defined keypoint of the same number will be redefined. Keypoints may be redefined only if it is not yet attached to a line or is not yet meshed. Solid modeling in a toroidal system is not recommended.

## Examples

Create keypoint at `(0, 1, 2)`

``` python
>>> knum = mapdl.k('', 0, 1, 2)
>>> knum
1
```

Create keypoint at `(10, 11, 12)` while specifying the keypoint number.

``` python
>>> knum = mapdl.k(5, 10, 11, 12)
>>> knum
5
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_K.html
