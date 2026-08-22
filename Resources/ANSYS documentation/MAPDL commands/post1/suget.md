---
apdl: "SUGET"
method: suget
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.suget
generated: 2026-08-22
tags: [mapdl-command]
---

# SUGET

PyMAPDL: `mapdl.suget(surfname='', rsetname='', parm='', geom='', **kwargs)`

Moves surface geometry and mapped results to an array parameter.

## Parameters

**surfname**: Eight character surface name.

**rsetname**: Eight character result name.

**parm**: APDL array parameter name (up to 32 characters).

**geom**

Switch controlling how data is written.

- `ON (or 1 or YES)` - Writes geometry data and interpolated results information to the parameter.
- `OFF (or 0 or NO)` - Writes only interpolated results information to the parameter. (Default)

## Notes

For `Geom` = OFF (or 0 or NO), only results information is written to this parameter.

For `Geom` = ON (or 1 or YES), both geometry data and results information are written to this parameter. Geometry data includes 7 data items: (GCX, GCY, GCZ, NORMX, NORMY, NORMZ, and DA). Results information is then written to the 8th column of the parameter. SetNames of GCX, GCY, GCZ, NORMX, NORMY, NORMZ, and DA are predefined and computed when [[sucr|SUCR]] is issued.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUGET.html
