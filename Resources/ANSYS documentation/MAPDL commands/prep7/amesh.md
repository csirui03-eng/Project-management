---
apdl: "AMESH"
method: amesh
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.amesh
generated: 2026-08-22
tags: [mapdl-command]
---

# AMESH

PyMAPDL: `mapdl.amesh(na1='', na2='', ninc='', **kwargs)`

Generates nodes and area elements within areas.

## Parameters

**na1**, **na2**, **ninc**: Mesh areas from `NA1` to `NA2` (defaults to `NA1` ) in steps of `NINC` (defaults to 1). If `NA1` = ALL, `NA2` and `NINC` are ignored and all selected areas ( [[asel|ASEL]] ) are meshed. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1` ( `NA2` and `NINC` are ignored).

## Notes

Any undefined nodes required for the generated elements are created and assigned the lowest available numbers.

This command is also valid fo r [rezoning](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_nlad/Hlp_G_ADVRZSMP.html).

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AMESH.html
