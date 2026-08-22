---
apdl: "ACCAT"
method: accat
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.accat
generated: 2026-08-22
tags: [mapdl-command]
---

# ACCAT

PyMAPDL: `mapdl.accat(na1='', na2='', **kwargs)`

Concatenates multiple areas in preparation for mapped meshing.

## Parameters

**na1**, **na2**: Areas to be concatenated. If `NA1` = ALL, `NA2` will be ignored and all selected areas ( [[asel|ASEL]] ) will be concatenated. If `NA1` = P, graphical picking is enabled and all remaining arguments are ignored (valid only in the GUI). A component name may also be substituted for `NA1` ( `NA2` is ignored).

## Notes

Concatenates multiple, adjacent areas (the input areas) into one area (the output area) in preparation for mapped meshing. A volume that contains too many areas for mapped meshing can still be mapped meshed if some of the areas in that volume are first concatenated (see [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_5.html#modmeshvaidck31400) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for details on mapped meshing restrictions).

Because of modeling restrictions that result from its use, **ACCAT** is meant to be used solely for meshing. Specifically, (a) the output area and any volumes that have the output area on their area list ( [[vlist|VLIST]] ) cannot be used as input to any other solid modeling operation (not even another **ACCAT** command); and (b) the output area cannot accept solid model boundary conditions ( [[da|DA]], [[sfa|SFA]] ).

The output area (or volumes which contain it) will be meshed ( [[amesh|AMESH]], [[vmesh|VMESH]] ) by meshing the input areas, which themselves must be meshable. The output area from the **ACCAT** operation will be coincident with the input areas and the input areas will be retained. Consider the [[aadd|AADD]] command instead of **ACCAT** if you wish to delete the input areas. When an **ACCAT** command is issued, volume area lists ( [[vlist|VLIST]] ) that contain all of the input areas will be updated so that the volume area lists refer to the output area instead of the input area. Deletion of the output area ( [[adele|ADELE]] ) effectively reverses the **ACCAT** operation and restores volume area lists to their original condition. **ACCAT** operations on pairs of adjacent four-sided areas automatically concatenate appropriate lines ( [[lccat|LCCAT]] ); in all other situations, line concatenations must be addressed by the user.

You can use the [[asel|ASEL]] command to select areas that were created by concatenation, and then follow it with an [[adele|ADELE]],ALL command to delete them. See [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_5.html#modmeshvaidck31400) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for a discussion on how to easily select and delete concatenated areas in one step.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_ACCAT.html
