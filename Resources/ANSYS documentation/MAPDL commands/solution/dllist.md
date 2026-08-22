---
apdl: "DLLIST"
method: dllist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dllist
generated: 2026-08-22
tags: [mapdl-command]
---

# DLLIST

PyMAPDL: `mapdl.dllist(line='', **kwargs)`

Lists DOF constraints on a line.

## Parameters

**line**: List constraints for this line. If ALL (default), list for all selected lines ( [[lsel|LSEL]] ). If `LINE` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `LINE`.

## Notes

Lists the degree of freedom constraints on a line previously specified with the [[dl|DL]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DLLIST.html
