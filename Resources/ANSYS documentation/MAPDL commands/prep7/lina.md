---
apdl: "LINA"
method: lina
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.lina
generated: 2026-08-22
tags: [mapdl-command]
---

# LINA

PyMAPDL: `mapdl.lina(nl='', na='', **kwargs)`

Finds the intersection of a line with an area.

## Parameters

**nl**: Number of line to be intersected. If `NL` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI).

**na**: Number of area to be intersected.

## Notes

Finds the intersection of a line with an area. New lines will be generated where the lines intersect the areas. If the regions of intersection are only points, new keypoints will be generated instead. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LINA.html
