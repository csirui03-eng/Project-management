---
apdl: "EORIENT"
method: eorient
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.eorient
generated: 2026-08-22
tags: [mapdl-command]
---

# EORIENT

PyMAPDL: `mapdl.eorient(etype='', dir_='', toler='', **kwargs)`

Reorients solid element normals.

## Parameters

**etype**

Specifies which elements to orient.

- `LYSL` - Specifies that layered solid elements will be oriented. This value is the default. Layered element types affected by this option include `SOLID185` with KEYOPT(3) = 1, `SOLID186` with KEYOPT(3) = 1, `SOLSH190`, `SOLID278` with KEYOPT(3) = 1 or 2, and `SOLID279` with KEYOPT(3) = 1 or 2.

**dir_**

The axis and direction for orientation, or an element number. If `Dir` is set to a positive number ( `n` ), then all eligible elements are oriented as similarly as possible to element `n`.

- `NEGX` - The element face with the outward normal most nearly parallel to the element coordinate system's negative x-axis is designated (reoriented) as face 1.
- `POSX` - The element face with the outward normal most nearly parallel to the element coordinate system's positive x-axis is designated (reoriented) as face 1.
- `NEGY` - The element face with the outward normal most nearly parallel to the element coordinate system's negative y-axis is designated (reoriented) as face 1..
- `POSY` - The element face with the outward normal most nearly parallel to the element coordinate system's positive y-axis is designated (reoriented) as face 1.
- `NEGZ` - (Default) The element face with the outward normal most nearly parallel to the element coordinate system's negative z-axis is designated (reoriented) as face 1.
- `POSZ` - The element face with the outward normal most nearly parallel to the element coordinate system's positive z-axis is designated (reoriented) as face 1.

**toler**: The maximum angle (in degrees) between the outward normal face and the target axis. Default is 90.0. Lower `TOLER` values will reduce the number of faces that are considered as the basis of element reorientation.

## Notes

**EORIENT** renumbers the element faces, designating the face most parallel to the XY plane of the element coordinate system (set with [[esys|ESYS]] ) as face 1 (nodes I-J-K-L, parallel to the layers in layered elements). It calculates the outward normal of each face and changes the node designation of the elements so the face with a normal most nearly parallel with and in the same general direction as the target axis becomes face 1.

The target axis, defined by `Dir`, is either the negative or positive indicated axis or the outward normal of face 1 of that element.

All layered solid elements in the selected set are considered for reorientation. The elements affected are layered structural solids ( `SOLID185`, `SOLID186` ), solid shell elements ( `SOLSH190` ), and layered thermal elements ( `SOLID278`, `SOLID279` ).

After reorienting elements, you should always display and graphically review results using the [[eshape|/ESHAPE]] command. When plotting models with many or symmetric layers, it may be useful to temporarily reduce the number of layers to two, with one layer being much thicker than the other.

You cannot use **EORIENT** to change the normal direction of any element that has a body or surface load. We recommend that you apply all of your loads only after ensuring that the element normal directions are acceptable.

Prisms and tetrahedrals are also supported for non-layered solid elements. Prisms are supported for layered solid elements, including layered `SOLID185`, layered `SOLID186`, layered `SOLID278`, layered `SOLID279`, and `SOLSH190`. However, layers parallel to the four-node face of the prism are not supported.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_EORIENT.html
