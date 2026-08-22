---
apdl: "SFEDELE"
method: sfedele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sfedele
generated: 2026-08-22
tags: [mapdl-command]
---

# SFEDELE

PyMAPDL: `mapdl.sfedele(elem='', lkey='', lab='', lcomp='', **kwargs)`

Deletes surface loads from elements.

## Parameters

**elem**: Element to which surface load deletion applies. If ALL, delete load from all selected elements ( [[esel|ESEL]] ). If `ELEM` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may be substituted for `ELEM`.

**lkey**: Load key associated with surface load (defaults to 1). If ALL, delete surface loads for all load keys. If [[sfcontrol|SFCONTROL]] is issued for selected elements, this value is the face number. If ALL, deletes the surface load based on `Lcomp`.

**lab**: Surface load label. If ALL, use all appropriate labels. See [[sfe|SFE]] for valid labels.

**lcomp**: Label of surface-load components. Valid when the surface load is defined via [[sfcontrol|SFCONTROL]]. Valid labels are NORM, TANX, TAXY when `KCSYS` = 0, LOCX, LOCY, LOCZ when `KCSYS` = 1, and USER when `KCSYS` = 2. ( `KCSYS` is specified when issuing [[sfcontrol|SFCONTROL]].) If ALL, deletes all component on the face defined by `LKEY`.

## Notes

Deletes surface loads from selected elements. See the [[sfdele|SFDELE]] command for an alternate surface load deletion capability based upon selected nodes.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFEDELE.html
