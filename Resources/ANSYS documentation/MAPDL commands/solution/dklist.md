---
apdl: "DKLIST"
method: dklist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_constraints.SolidConstraints.dklist
generated: 2026-08-22
tags: [mapdl-command]
---

# DKLIST

PyMAPDL: `mapdl.dklist(kpoi='', **kwargs)`

Lists the DOF constraints at keypoints.

## Parameters

**kpoi**: List constraints for this keypoint. If ALL (default), list for all selected keypoints ( [[ksel|KSEL]] ). If `KPOI` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `KPOI`.

## Notes

Listing applies to the selected keypoints ( [[ksel|KSEL]] ) and the selected degree of freedom labels ( [[dofsel|DOFSEL]] ).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_DKLIST.html
