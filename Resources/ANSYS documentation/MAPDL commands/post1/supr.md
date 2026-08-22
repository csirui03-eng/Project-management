---
apdl: "SUPR"
method: supr
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.supr
generated: 2026-08-22
tags: [mapdl-command]
---

# SUPR

PyMAPDL: `mapdl.supr(surfname='', rsetname='', **kwargs)`

Print global status, geometry information and/or result information.

## Parameters

**surfname**: Eight character surface name. If `SurfName` = ALL, repeat printout for all selected surfaces.

**rsetname**: Eight character result set name.

## Notes

When no arguments are specified, **SUPR** generates a global status summary of all defined surfaces. If only `SurfName` is specified, the geometry information for that surface is printed. If both `SurfName` and `RSetName` are specified, the value of the results set at each point, in addition to the geometry information, is printed.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUPR.html
