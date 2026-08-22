---
apdl: "SFDELE"
method: sfdele
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.fe_surface_loads.FeSurfaceLoads.sfdele
generated: 2026-08-22
tags: [mapdl-command]
---

# SFDELE

PyMAPDL: `mapdl.sfdele(nlist='', lab='', **kwargs)`

Deletes surface loads.

## Parameters

**nlist**

Label defining where to find the list of nodes:

- `ALL` - Use all selected nodes ( [[nsel|NSEL]] ). A component label may be substituted for `Nlist`.

**lab**: Valid surface load label. If ALL, use all appropriate labels. See the [[sf|SF]] command for labels.

## Notes

Deletes surface loads as applied via [[sf|SF]]. Loads are deleted only for the specified nodes on external faces of selected area and volume elements. For shell elements, if the specified nodes include face one (which is usually the bottom face) along with other faces (such as edges), only the loads on face one will be deleted. The element faces are determined from the list of selected nodes as described for [[sf|SF]]. Issue [[sfedele|SFEDELE]] to delete loads explicitly by element faces.

This command is also valid in PREP7.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_SFDELE.html
