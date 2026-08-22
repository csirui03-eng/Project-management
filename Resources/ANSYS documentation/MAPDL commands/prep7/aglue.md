---
apdl: "AGLUE"
method: aglue
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.aglue
generated: 2026-08-22
tags: [mapdl-command]
---

# AGLUE

PyMAPDL: `mapdl.aglue(na1='', na2='', na3='', na4='', na5='', na6='', na7='', na8='', na9='', **kwargs)`

Generates new areas by "gluing" areas.

## Parameters

**na1**, **na2**, **na3**, **na4**, **na5**, **na6**, **na7**, **na8**, **na9**: Numbers of the areas to be glued. If `NA1` = ALL, all selected areas will be glued ( `NA2` to `NA9` will be ignored). If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1`.

## Notes

Use of the **AGLUE** command generates new areas by "gluing" input areas. The glue operation redefines the input areas so that they share lines along their common boundaries. The new areas encompass the same geometry as the original areas. This operation is only valid if the intersection of the input areas are lines along the boundaries of those areas. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to new entities generated.

The **AGLUE** command results in the merging of lines and keypoints at the common area boundaries. The lines and keypoints of the lower numbered area will be kept. This means one must be aware of area numbering when multiple **AGLUE** commands are applied to avoid any "ungluing" of geometry.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_AGLUE.html
