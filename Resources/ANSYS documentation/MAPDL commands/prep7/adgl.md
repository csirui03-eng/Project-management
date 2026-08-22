---
apdl: "ADGL"
method: adgl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.adgl
generated: 2026-08-22
tags: [mapdl-command]
---

# ADGL

PyMAPDL: `mapdl.adgl(na1='', na2='', ninc='', **kwargs)`

Lists keypoints of an area that lie on a parametric degeneracy.

## Parameters

**na1**, **na2**, **ninc**: List keypoints that lie on a parametric degeneracy on areas from `NA1` to `NA2` (defaults to `NA1` ) in steps of `NINC` (defaults to 1). If `NA1` = ALL (default), `NA2` and `NINC` will be ignored and keypoints on all selected areas ( [[asel|ASEL]] ) will be listed. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may be substituted in `NA1` ( `NA2` and `NINC` will be ignored).

## Notes

See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for details on parametric degeneracies.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ADGL.html
