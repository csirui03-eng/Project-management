---
apdl: "AINV"
method: ainv
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.ainv
generated: 2026-08-22
tags: [mapdl-command]
---

# AINV

PyMAPDL: `mapdl.ainv(na='', nv='', **kwargs)`

Finds the intersection of an area with a volume.

## Parameters

**na**: Number of area to be intersected. If P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI).

**nv**: Number of volume to be intersected.

## Notes

New areas will be generated where the areas intersect the volumes. If the regions of intersection are only lines, new lines will be generated instead. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AINV.html
