---
apdl: "LCCAT"
method: lccat
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.meshing.Meshing.lccat
generated: 2026-08-22
tags: [mapdl-command]
---

# LCCAT

PyMAPDL: `mapdl.lccat(nl1='', nl2='', **kwargs)`

Concatenates multiple lines into one line for mapped meshing.

## Parameters

**nl1**, **nl2**: Lines to be concatenated. If `NL1` = ALL, `NL2` is ignored and all selected lines ( [[lsel|LSEL]] ) are concatenated. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1` ( `NL2` is ignored).

## Notes

Concatenates multiple, adjacent lines (the input lines) into one line (the output line) in preparation for mapped meshing. An area that contains too many lines for mapped meshing can still be mapped meshed if some of the lines in that area are first concatenated (see [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for details on mapped meshing restrictions).

**LCCAT** is meant to be used solely for meshing and cannot be used for any other purposes. Specifically, (a) the output line and any areas that have the output line on their line list ( [[alist|ALIST]] ) cannot be used as input to any other solid modeling operation (not even another **LCCAT** command); and (b) the output line cannot accept solid model boundary conditions ( [[dl|DL]], [[sfl|SFL]] ).

The output line will take on the element divisions of the input lines and will not accept element divisions that are directly assigned ( [[lesize|LESIZE]] ). The output line from the **LCCAT** operation will be coincident with the input lines and the input lines will be retained. Consider the [[lcomb|LCOMB]] command instead of **LCCAT** if you wish to delete the input lines and if the lines to be combined have similar slopes at the common keypoint(s). When an **LCCAT** command is issued, area line lists ( [[alist|ALIST]] ) that contain all of the input lines will be updated so that the area line lists refer to the output line instead of the input lines. Deletion of the output line ( [[ldele|LDELE]] ) effectively reverses the **LCCAT** operation and restores area line lists to their original condition.

You can use the [[lsel|LSEL]] command to select lines that were created by concatenation, and then follow it with an [[ldele|LDELE]],ALL command to delete them. Also see [Meshing Your Solid Model](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD7_8.html) in the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for a discussion on how to easily select and delete concatenated lines in one step.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LCCAT.html
