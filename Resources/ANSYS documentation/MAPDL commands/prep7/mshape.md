---
apdl: "MSHAPE"
method: mshape
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.mshape
generated: 2026-08-22
tags: [mapdl-command]
---

# MSHAPE

PyMAPDL: `mapdl.mshape(key='', dimension='', **kwargs)`

For elements that support multiple shapes, specifies the element shape to be used for meshing.

## Parameters

**key**

Key indicating the element shape to be used:

- `0` - Mesh with quadrilateral-shaped elements when `Dimension` = 2D mesh with hexahedral- shaped elements when `Dimension` = 3D.
- `1` - Mesh with triangle-shaped elements when `Dimension` = 2D mesh with tetrahedral-shaped elements when `Dimension` = 3D.

**dimension**

Specifies the dimension of the model to be meshed:

- `2D` - 2D model (area mesh).
- `3D` - 3D model (volume mesh).

## Notes

If no value is specified for `Dimension` the value of `KEY` determines the element shape that will be used for both 2D and 3D meshing. In other words, if you specify **MSHAPE**,0, quadrilateral-shaped and hexahedral-shaped elements will be used. If you specify **MSHAPE**,1, triangle-shaped and tetrahedral-shaped elements will be used.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MSHAPE.html
