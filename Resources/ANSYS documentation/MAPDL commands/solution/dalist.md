---
apdl: "DALIST"
method: dalist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dalist
generated: 2026-08-22
tags: [mapdl-command]
---

# DALIST

PyMAPDL: `mapdl.dalist(area='', **kwargs)`

Lists the DOF constraints on an area.

## Parameters

**area**: List constraints for this area. If ALL (default), list for all selected areas ( [[asel|ASEL]] ). If `P1` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `AREA`.

## Notes

Lists the degree of freedom constraints on an area previously specified with the [[da|DA]] command.

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DALIST.html
