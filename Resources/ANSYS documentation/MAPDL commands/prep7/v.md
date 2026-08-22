---
apdl: "V"
method: v
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.v
generated: 2026-08-22
tags: [mapdl-command]
---

# V

PyMAPDL: `mapdl.v(p1='', p2='', p3='', p4='', p5='', p6='', p7='', p8='', **kwargs)`

Defines a volume through keypoints.

## Parameters

**p1**: Keypoint defining starting corner of volume. If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**p2**: Keypoint defining second corner of volume.

**p3**: Keypoint defining third corner of volume.

**p4**: Keypoint defining fourth corner of volume.

**p5**: Keypoint defining fifth corner of volume.

**p6**: Keypoint defining sixth corner of volume.

**p7**: Keypoint defining seventh corner of volume.

**p8**: Keypoint defining eighth corner of volume.

## Returns

`int`: Volume number of the generated volume.

## Notes

**Notes**

Defines a volume (and its corresponding lines and areas) through eight (or fewer) existing keypoints. Keypoints must be input in a continuous order. The order of the keypoints should be around the bottom and then the top. Missing lines are generated "straight" in the active coordinate system and assigned the lowest available numbers ( [[numstr|NUMSTR]] ). Missing areas are generated and assigned the lowest available numbers.

Solid modeling in a toroidal coordinate system is not recommended.

Certain faces may be condensed to a line or point by repeating keypoints. For example, use **V**, `P1`, `P2`, `P3`, `P3`, `P5`, `P6`, `P7`, `P7` for a triangular prism or **V**, `P1`, `P2`, `P3`, `P3`, `P5`, `P5`, `P5`, `P5` for a tetrahedron.

Using keypoints to produce partial sections in [[csys|CSYS]] = 2 can generate anomalies; check the resulting volumes carefully.

## Examples

Create a simple cube volume.

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.k("", 1, 1, 0)
>>> k3 = mapdl.k("", 0, 1, 0)
>>> k4 = mapdl.k("", 0, 0, 1)
>>> k5 = mapdl.k("", 1, 0, 1)
>>> k6 = mapdl.k("", 1, 1, 1)
>>> k7 = mapdl.k("", 0, 1, 1)
>>> v0 = mapdl.v(k0, k1, k2, k3, k4, k5, k6, k7)
>>> v0
1
```

Create a triangular prism

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.k("", 1, 1, 0)
>>> k3 = mapdl.k("", 0, 1, 0)
>>> k4 = mapdl.k("", 0, 0, 1)
>>> k5 = mapdl.k("", 1, 0, 1)
>>> k6 = mapdl.k("", 1, 1, 1)
>>> k7 = mapdl.k("", 0, 1, 1)
>>> v1 = mapdl.v(k0, k1, k2, k2, k4, k5, k6, k6)
>>> v1
2
```

Create a tetrahedron

``` python
>>> k0 = mapdl.k("", 0, 0, 0)
>>> k1 = mapdl.k("", 1, 0, 0)
>>> k2 = mapdl.k("", 1, 1, 0)
>>> k3 = mapdl.k("", 0, 0, 1)
>>> v2 = mapdl.v(k0, k1, k2, k2, k3, k3, k3, k3)
>>> v2
3
```

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_V.html
