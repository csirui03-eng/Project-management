---
apdl: "APLOT"
method: aplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.areas.Areas.aplot
generated: 2026-08-22
tags: [mapdl-command]
---

# APLOT

PyMAPDL: `mapdl.aplot(na1='', na2='', ninc='', degen='', scale='', **kwargs)`

Displays the selected areas.

## Parameters

**na1**, **na2**, **ninc**: Displays areas from `NA1` to `NA2` (defaults to `NA1` ) in steps of `NINC` (defaults to 1). If `NA1` = ALL (default), `NA2` and `NINC` are ignored and all selected areas ( [[asel|ASEL]] ) are displayed.

**degen**

Degeneracy marker:

- `(blank)` - No degeneracy marker is used (default).
- `DEGE` - A red star is placed on keypoints at degeneracies (see the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) ). Not available if [[facet|/FACET]],WIRE is set.

**scale**: Scale factor for the size of the degeneracy-marker star. The scale is the size in window space (-1 to 1 in both directions) (defaults to.075).

## Notes

This command is valid in any processor. The degree of tessellation used to plot the selected areas is set through the [[facet|/FACET]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_APLOT.html
