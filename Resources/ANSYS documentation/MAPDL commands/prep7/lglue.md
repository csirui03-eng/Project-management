---
apdl: "LGLUE"
method: lglue
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.lglue
generated: 2026-08-22
tags: [mapdl-command]
---

# LGLUE

PyMAPDL: `mapdl.lglue(nl1='', nl2='', nl3='', nl4='', nl5='', nl6='', nl7='', nl8='', nl9='', **kwargs)`

Generates new lines by "gluing" lines.

## Parameters

**nl1**, **nl2**, **nl3**, **nl4**, **nl5**, **nl6**, **nl7**, **nl8**, **nl9**: Numbers of the lines to be glued. If `NL1` = ALL, all selected lines will be glued ( `NL2` to `NL9` will be ignored). If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1`.

## Notes

Use of the **LGLUE** command generates new lines by "gluing" input lines. The glue operation redefines the input lines so that they share keypoints at their common ends. The new lines encompass the same geometry as the original lines. This operation is only valid if the intersections of the input lines are keypoints at the ends of those lines. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

The **LGLUE** command results in the merging of keypoints at the common end of the lines. The keypoints of the lower numbered line will be kept. This means one must be aware of line numbering when multiple **LGLUE** commands are applied to avoid any "ungluing" of geometry.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LGLUE.html
