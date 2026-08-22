---
apdl: "VPLOT"
method: vplot
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.volumes.Volumes.vplot
generated: 2026-08-22
tags: [mapdl-command]
---

# VPLOT

PyMAPDL: `mapdl.vplot(nv1='', nv2='', ninc='', degen='', scale='', **kwargs)`

PyMAPDL overrides `mapdl.vplot` with its own wrapper, so the signature above is not what `mapdl.vplot` runs. Reach the APDL command as text: `mapdl.run("VPLOT,...")`.

Displays the selected volumes.

## Parameters

**nv1**, **nv2**, **ninc**: Display volumes from `NV1` to `NV2` (defaults to `NV1` ) in steps of `NINC` (defaults to 1). If `NV1` = ALL (default), `NV2` and `NINC` are ignored and all selected volumes ( [[vsel|VSEL]] ) are displayed.

**degen**

Degeneracy marker:

- `(blank)` - No degeneracy marker is used (default).
- `DEGE` - A red star is placed on keypoints at degeneracies (see the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html)). Not available if [[facet|/FACET]],WIRE is set.

**scale**: Scale factor for the size of the degeneracy-marker star. The scale is the size in window space (-1 to 1 in both directions) (defaults to.075).

## Notes

Displays selected volumes. (Only volumes having areas within the selected area set ( [[asel|ASEL]] ) will be plotted.) With PowerGraphics on ( [[graphics|/GRAPHICS]],POWER), **VPLOT** will display only the currently selected areas. This command is also a utility command, valid anywhere. The degree of tessellation used to plot the volumes is set through the [[facet|/FACET]] command.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_VPLOT.html
