---
apdl: "GEOM"
method: geom
group: aux12
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux12.radiation_matrix_method.RadiationMatrixMethod.geom
generated: 2026-08-22
tags: [mapdl-command]
---

# GEOM

PyMAPDL: `mapdl.geom(k2d='', ndiv='', **kwargs)`

Defines the geometry specifications for the radiation matrix calculation.

## Parameters

**k2d**

Dimensionality key:

- `0` - 3D geometry (default)
- `1` - 2D geometry (plane or axisymmetric)

**ndiv**: Number of divisions in an axisymmetric model. Used only with `K2D` = 1. Defaults to 0 (2D plane). The 2D model is internally expanded to a 3D model based on the number of divisions specified (6 (equation omitted) `NDIV` (equation omitted) 90). For example, `NDIV` of 6 is internally represented by six 60° sections.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_GEOM.html
