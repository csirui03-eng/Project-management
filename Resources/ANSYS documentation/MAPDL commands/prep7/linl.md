---
apdl: "LINL"
method: linl
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.linl
generated: 2026-08-22
tags: [mapdl-command]
---

# LINL

PyMAPDL: `mapdl.linl(nl1='', nl2='', nl3='', nl4='', nl5='', nl6='', nl7='', nl8='', nl9='', **kwargs)`

Finds the common intersection of lines.

## Parameters

**nl1**, **nl2**, **nl3**, **nl4**, **nl5**, **nl6**, **nl7**, **nl8**, **nl9**: Numbers of lines to be intersected. If `NL1` = ALL, find the intersection of all selected lines and `NL2` to `NL9` are ignored. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1`.

## Notes

Finds the common (not pairwise) intersection of lines. The common intersection is defined as the regions shared (in common) by all lines listed on this command. New lines will be generated where the original lines intersect. If the regions of intersection are only points, new keypoints will be generated instead. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. See the [[boptn|BOPTN]] command for the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LINL.html
