---
apdl: "VTYPE"
method: vtype
group: aux12
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux12.radiation_matrix_method.RadiationMatrixMethod.vtype
generated: 2026-08-22
tags: [mapdl-command]
---

# VTYPE

PyMAPDL: `mapdl.vtype(nohid='', nzone='', **kwargs)`

Specifies the viewing procedure used to determine the form factors for the Radiation Matrix method.

## Parameters

**nohid**

Type of viewing procedure:

- `0` - Hidden procedure.
- `1` - Non-hidden (faster, but less general) procedure.

**nzone**: Number of sampling zones for the hidden procedure (100 maximum for 3D, 1000 maximum for 2D). Defaults to 20 for 3D, 200 for 2D. Number of points is 2\* `NZONE` for 2D and 2\* `NZONE` \*( `NZONE` +1) for 3D.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VTYPE.html
