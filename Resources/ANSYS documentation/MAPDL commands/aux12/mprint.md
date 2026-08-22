---
apdl: "MPRINT"
method: mprint
group: aux12
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.aux12.radiation_matrix_method.RadiationMatrixMethod.mprint
generated: 2026-08-22
tags: [mapdl-command]
---

# MPRINT

PyMAPDL: `mapdl.mprint(key='', **kwargs)`

Specifies that radiation matrices are to be printed.

## Parameters

**key**

Print key:

- `0` - Do not print matrices.
- `1` - Print matrices.

## Notes

Specifies that the element and node radiation matrices are to be printed when the [[write|WRITE]] command is issued. If `KEY` = 1, form factor information for each element will also be printed.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_MPRINT.html
