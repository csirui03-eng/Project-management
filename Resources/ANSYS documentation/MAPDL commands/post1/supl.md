---
apdl: "SUPL"
method: supl
group: post1
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.post1.surface_operations.SurfaceOperations.supl
generated: 2026-08-22
tags: [mapdl-command]
---

# SUPL

PyMAPDL: `mapdl.supl(surfname='', rsetname='', kwire='', **kwargs)`

Plot result data on all selected surfaces or on a specified surface.

## Parameters

**surfname**: Eight-character surface name. ALL plots all selected surfaces.

**rsetname**: Eight-character result name.

**kwire**

Plot in context of model.

- `0` - Plot results without the outline of selected elements.
- `1` - Plot results with the outline of selected elements.

## Notes

If `RSetName` is not specified, the surface geometry is plotted. If the Setname portion of the argument is a vector prefix (that is, if result sets of name SetNameX, SetNameY, and SetNameZ exist), Mechanical APDL plots the vectors on the surface as arrows. For example, **SUPL**,ALL,NORM plots the surface normals as vectors on all selected surfaces, as NORMX, NORMY, and NORMZ are predefined geometry items.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SUPL.html
