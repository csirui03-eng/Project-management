---
apdl: "FKLIST"
method: fklist
group: solution
source: PyMAPDL 0.74.1 docstrings, pandoc 3.9.0.2, ansys.mapdl.core._commands.solution.solid_forces.SolidForces.fklist
generated: 2026-08-22
tags: [mapdl-command]
---

# FKLIST

PyMAPDL: `mapdl.fklist(kpoi='', lab='', **kwargs)`

Lists the forces at keypoints.

## Parameters

**kpoi**: List forces at this keypoint. If ALL (default), list for all selected keypoints ( [[ksel|KSEL]] ). If `KPOI` = P, graphical picking is enabled and all remaining command fields are ignored (valid only in the GUI). A component name may also be substituted for `KPOI`.

**lab**: Force label to be listed (defaults to ALL). See the [[dofsel|DOFSEL]] command for labels.

## Notes

Listing applies to the selected keypoints ( [[ksel|KSEL]] ) and the selected force labels ( [[dofsel|DOFSEL]] ).

This command is valid in any processor.

Ansys help: https://ansyshelp.ansys.com/Views/Secured/corp/v232/en//ans_cmd/Hlp_C_FKLIST.html
