---
apdl: "ESIZE"
method: esize
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.esize
generated: 2026-08-22
tags: [mapdl-command]
---

# ESIZE

PyMAPDL: `mapdl.esize(size='', ndiv='', **kwargs)`

Specifies the default number of line divisions.

## Parameters

**size**: Default element edge length on surface boundaries (that is, lines). Divisions are automatically calculated (rounded upward to next integer) from line lengths. If `SIZE` is zero (or blank), use `NDIV`.

**ndiv**: Default number of element divisions along region boundary lines. Not used if `SIZE` is input.

## Notes

Specifies the default number of line divisions (elements) to be generated along the region boundary lines. The number of divisions may be defined directly or automatically calculated. Divisions defined directly for any line ( [[lesize|LESIZE]], [[kesize|KESIZE]], etc.) are retained. For adjacent regions, the divisions assigned to the common line for one region are also used for the adjacent region. See the [[mopt|MOPT]] command for additional meshing options.

For free meshing operations, if smart element sizing is being used ( [[smrtsize|SMRTSIZE]] ) and **ESIZE**, `SIZE` has been specified, `SIZE` will be used as a starting element size, but will be overridden (that is, a smaller size may be used) to accommodate curvature and small features.

This command is also valid for [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ESIZE.html
