---
apdl: "LOVLAP"
method: lovlap
group: prep7
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.prep7.booleans.Booleans.lovlap
generated: 2026-08-22
tags: [mapdl-command]
---

# LOVLAP

PyMAPDL: `mapdl.lovlap(nl1='', nl2='', nl3='', nl4='', nl5='', nl6='', nl7='', nl8='', nl9='', **kwargs)`

Overlaps lines.

## Parameters

**nl1**, **nl2**, **nl3**, **nl4**, **nl5**, **nl6**, **nl7**, **nl8**, **nl9**: Numbers of lines to be overlapped. If `NL1` = ALL, `NL2` to `NL9` are ignored and all selected lines are overlapped. If `NL1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `NL1`.

## Notes

Overlaps lines. Generates new lines which encompass the geometry of all the input lines. The new lines are defined by the regions of intersection of the input lines, and by the complementary (non- intersecting) regions. See the [Modeling and Meshing Guide](https://ansyshelp.ansys.com/Views/Secured/corp/v232/en/ans_mod/Hlp_G_MOD14.html) for an illustration. This operation is only valid when the region of intersection is a line. See the [[boptn|BOPTN]] command for an explanation of the options available to Boolean operations. Element attributes and solid model boundary conditions assigned to the original entities will not be transferred to the new entities generated.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_LOVLAP.html
